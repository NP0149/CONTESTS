# Minimum cost to convert

[Problem Link](https://leetcode.com/problems/minimum-cost-to-convert-string-ii/description/?envType=daily-question&envId=2026-01-31)

```
import java.util.*;

class Solution {

    static class TrieNode {
        TrieNode[] next = new TrieNode[26];
        int id = -1; // substring id
    }

    public long minimumCost(
            String source,
            String target,
            String[] original,
            String[] changed,
            int[] cost) {

        int n = source.length();
        long INF = (long) 1e18;

        // 1️⃣ Give each unique substring an id
        Map<String, Integer> idMap = new HashMap<>();
        int idx = 0;

        for (String s : original) {
            if (!idMap.containsKey(s)) idMap.put(s, idx++);
        }
        for (String s : changed) {
            if (!idMap.containsKey(s)) idMap.put(s, idx++);
        }

        int m = idx;

        // 2️⃣ Floyd-Warshall on substring graph
        long[][] dist = new long[m][m];
        for (int i = 0; i < m; i++) {
            Arrays.fill(dist[i], INF);
            dist[i][i] = 0;
        }

        for (int i = 0; i < original.length; i++) {
            int u = idMap.get(original[i]);
            int v = idMap.get(changed[i]);
            dist[u][v] = Math.min(dist[u][v], cost[i]);
        }

        for (int k = 0; k < m; k++) {
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < m; j++) {
                    if (dist[i][k] + dist[k][j] < dist[i][j]) {
                        dist[i][j] = dist[i][k] + dist[k][j];
                    }
                }
            }
        }

        // 3️⃣ Build Trie for original substrings
        TrieNode root = new TrieNode();
        for (Map.Entry<String, Integer> e : idMap.entrySet()) {
            String s = e.getKey();
            TrieNode cur = root;
            for (char c : s.toCharArray()) {
                int d = c - 'a';
                if (cur.next[d] == null) cur.next[d] = new TrieNode();
                cur = cur.next[d];
            }
            cur.id = e.getValue();
        }

        // 4️⃣ DP
        long[] dp = new long[n + 1];
        Arrays.fill(dp, INF);
        dp[0] = 0;

        for (int i = 0; i < n; i++) {
            if (dp[i] == INF) continue;

            // Case 1: single character match
            if (source.charAt(i) == target.charAt(i)) {
                dp[i + 1] = Math.min(dp[i + 1], dp[i]);
            }

            // Case 2: substring conversion
            TrieNode sNode = root;
            TrieNode tNode = root;

            for (int j = i; j < n; j++) {
                int a = source.charAt(j) - 'a';
                int b = target.charAt(j) - 'a';

                if (sNode.next[a] == null || tNode.next[b] == null) break;

                sNode = sNode.next[a];
                tNode = tNode.next[b];

                if (sNode.id != -1 && tNode.id != -1) {
                    long cst = dist[sNode.id][tNode.id];
                    if (cst != INF) {
                        dp[j + 1] = Math.min(dp[j + 1], dp[i] + cst);
                    }
                }
            }
        }

        return dp[n] == INF ? -1 : dp[n];
    }
}

```
