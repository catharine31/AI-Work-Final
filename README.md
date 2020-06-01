#### 計算機程式期末報告
<h1>
  主題: 預測nba球賽結果
</h1>
<h1>
  組員與分工: 
</h1>
  <br>
  106306049 資管三 曾韻宸: 資料蒐集、資料整理 <br>
  106306030 資管三 詹雅芸: 訓練模型、預測結果 <br>
  106306020 資管三 張芯慈: 資料蒐集、資料整理 <br>
  108363092 企研一 陳宇慈: 訓練模型、預測結果 <br>
<h1>
  內容:
</h1>

- 資料蒐集:
  <br>
    我們使用 nba-api(https://github.com/swar/nba_api) 搜集資料，接著做資料整理，所使用的資料為各隊伍和各球員在各場比賽中的戰績表現(例如投籃命中       率、進攻、防守等資訊)
  <br>
      nba-api資料來源參考:  <br>
      nba_api/docs/nba_api/stats/endpoints/playergamelog.md <br>
      nba_api/docs/nba_api/stats/endpoints/boxscoreadvancedv2.md <br>
      nba_api/docs/nba_api/stats/endpoints/teamgamelog.md <br>
 

- 資料整理:
    <br>
    playergamelog資料中紀錄每個球員在每一場比賽中的一般數據 <br>
    team_game_table資料中記錄每支球隊在每一場比賽中的一般數據 <br>
    AdvancedIndex資料中紀錄每個球員在每一場比賽中的進階數據 <br>
    Player_std資料中紀錄單一球隊中球員之間各種表現的標準差，因為我們想了解隊伍中球員表現的差異是否會影像球隊的表現，故想將單一隊伍中球員之間的表現差     異也納入模型訓練 <br>
    <br>
    - 首先我們先從api蒐集到playergamelog、team_game_table與AdvancedIndex，<br>
    接著把playergamelog與AdvancedIndex根據球員與比賽整合成一個table， <br>
    接下來我們對上一步整合好的table根據球隊與比賽分群，計算每一群的標準差，得到的每支球隊在每一場比賽中的球員表現標準差，
    接著，我們把接著，我們把計算好的標準差Player_std與team_game_table根據球隊與比賽整合成一個table。<br>
    - 預測分數的部分，我們想使用欲預測的球隊A與他的比賽對手B過往的比賽紀錄之平均表現來預測接下來這場比賽A的得分,
    所以我們先找出所有球隊與其比賽對手在某場比賽之前的過往資料，接著對這些資料取平均，然侯再把某場比賽的實際得分加到資料中，
    實際得分這個欄位就會是最終模型要預測的y，其他欄位則是輸入的資料x。 <br>
    
    
- 模型架構:
  <br>
  
    
    



