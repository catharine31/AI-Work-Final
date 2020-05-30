#### 計算機程式期末報告
<h1>
  主題: 預測nba球賽結果
</h1>

<h1>
  內容:
</h1>
  <div>
    資料蒐集:
    <br>
    我們使用 nba-api(https://github.com/swar/nba_api) 搜集資料，接著做資料整理，所使用的資料為各隊伍和各球員在各場比賽中的戰績表現(例如投籃命中率、‵     進攻、防守等資訊)
    nba-api資料來源參考:  nba_api/docs/nba_api/stats/endpoints/playergamelog.md
                 nba_api/docs/nba_api/stats/endpoints/boxscoreadvancedv2.md
                 nba_api/docs/nba_api/stats/endpoints/teamgamelog.md
                
  </div>  
  
 

<br>
「各球員在各場比賽中的戰績表現」這份資料：我們想了解隊伍中球員表現的差異是否會影像球隊的表現，故將單一隊伍中球員之間的表現差異也納入模型訓練，因此對單一球隊中球員之間各種表現的標準差做計算
<br>
接著，我們提取「球隊中球員間表現各項戰績的標準差」和「隊伍在各場比賽中的戰績表現」做資料的合併，以訓練模型
