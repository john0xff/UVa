Beverage Contest II - Solution Sketch 

    Problem A - Attack and Split

 小夥伴們快來翻譯 有支持 latex 語法嗎？
 題目大意：有一隻史萊姆†可以進行分裂和合併，大小為 x 的史萊姆可以分裂成兩個小史萊姆 y 和 z，滿足 x = y + z。當兩個史萊姆大小 p, q 合併時，新的史萊姆為 r = p xor q。請問是否存在數次的分裂和合併，所有史萊姆都消失！

    對於一種合法解 {a1, a2}，則 {a1-1, 1, a2-1, 1} 也一定會合法，不斷地拆分下去，所有史萊姆的大小都是 1，也發現到總和一定是偶數。因此只要判斷總和的奇偶數。

    這樣會沒辦法確定無解真的無解吧XD

    Problem B - Dreamoon's Criterion

夢月解題目會根據夢月法則？如果題目需要花費大於等於 t 的時間，則定義題目難度為 hard，反之為 easy。小番茄 (求解釋) 準備 n 個題目請求夢月協助，但隨著每解一題，下一題的難度會隨著疲累值增加，疲累值為一個等差為 k 個數列。只打算解決 easy 的題目，請問在相同的 k 下，不同的 t 分別能解決的最多題數。

    t 越大，能解的題目肯定越多！難度越低的題目一定會選，因此前 i 小難度的題目都會被挑。利用類似求方程式值的方式 (隨便講講，別太在意 f(x) = a0 + a1x + a2x^2 + a3x^3 ... + anx^n，可以在 O(n) 完成的方法) 下去猜測？維護已選題目如果增加 k 不大於 t 且下一個題目難度也小於 t，則所有已選難度都增加 k！離線處理，將詢問的 t 由小到大排序，掃描過去？

    Problem C - Heap Like Sort

    求解釋解釋範例測資，外包翻譯沒看懂 :3

    Problem D - A Parking Problem

停車場有 n 個位置呈現單方向，由入口到出口分別編號為 1 到 n，現在有 m 名駕駛準備要停車，每名駕駛的停車方案都會先開到偏愛的車位上，如果發現已經有人停過，則會往後找一個空車位。由於駕駛入停車場任意順序。請問從 m 個駕駛中挑出 n 個駕駛，任意進入停車場，按照他們各自偏愛的停車方法，每一位都有停車位的合法選擇駕駛的方案數。

    維護前 i 個位置中，挑選 j 名駕駛的方法數！dp[i][j] 表示前 i 個位置，挑選 j 個駕駛的方法數，並且滿足 j >= i，否則會有留空一格造成後續的非法解。窮舉下一個位置挑選的人數 k，得到 dp[i+1][j+k] += (dp[i][j] * C[A[i+1]][k])%MOD;

    Problem E - Kirino in Google Code Jam

原題是對於任意平面點，找到要移除最小的平面點，使得自己在凸包邊緣上。標準的極角排序，維護 180 度以內 (半平面) 的點個數。

    等等，challenge 這一題時，自己的代碼也 WA 了！

    一開始誤以為是 index out of bound，assert() 下去都沒發生。後來估計是 atan2(y, x) 的誤差，對此誤差早有耳聞，解題撞壁的機會很低。咱很蠢，隨機生了 1000 萬個平面點，按照 atan2 排序，檢查相鄰兩個座標的外積 (叉積) 是否為逆時針，跑一次隨機生成大概能爆出一個誤差的相鄰點，十來次得到 n 個點，隨機組合這 n 個點於四個象限，再亂撒少數個點，再跟自己撰寫的代碼做比對 (中間又測了上萬組)。

    Problem F - No challenge No life 

    Problem G - Strange Permutations

排列 1 到 n 的整數，使得相鄰兩數互質，部分位置一定要填入某些數字，請問剩餘數字的填法方案數為何？

    bitmask 下去 dp[N][1<<N][N]，dp[i][j][k] 表示前 i 個位置，已經使用的數字狀態 j，最後一個數字 k。不曉得需不需要滾動，記憶體用量驚人。萬萬沒想到，撰寫過程中坑了一個建表的 gcd[20][20]，當 n = 20 時，直接 index out of bound，先撇開這個蠢錯。滾動數組下去玩，真是誘人的時間限制，再次得到 9.990s TLE 的事蹟 ！仔細想想，運算過程中只出現加法，將 mod 運算替換成條件判斷 + 減法，

    Problem H - Tomato's Criterion

    Problem I - Cow Families

    Problem J - Domino Tableaux

    Problem K - Increasing Subsequences

    Problem L - Domino Rotations

