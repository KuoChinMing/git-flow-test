# Git Flow

1. 開啟本地端 `develop` 分支，`develop` 分支是開發的主要分支，當有新功能或重要功能完成時，會 merge 到 `develop` 分支
2. 有新功能的話，在 `develop` 分支 checkout 一個 `feature` 分支，並切換到 `feature` 分支，`feature` 分支就是開發新功能的分支
3. 當 `feature` 的新功能完成時，會切換到 `develop` 分支，並 merge  `feature` 分支
3.5. 當 `feature` 尚在開發時，又有新功能需要開發（或多人開發），可以再開一個 `feature2` 的分支，來進行開發，操作流程都與`feature` 相同
1. 當 `develop` 開發到一個段落要釋出新版本時，從 `develop` 分支開出一個 release 分支並附註版本號 `release/0.1.0`，穩定後，再讓 `master` 與 `develop` merge 回 `release` 分支 
（換句話說， `release` 分支是用來存放*準備要發布版本*的分支，要夠穩定才能 merge 回 `master`，在實際操作情況，可以簡單理解成「自己」覺得穩定的版本發佈一版在 `release`，當 PM 或其他人還有 feedback 的時候，`release` 就繼續往後走，直到全部都穩定後在 merge 回 `master`）
5. 當 `master` 穩定版本發布後還有 bug 或需要緊急處理的事情，就從 `master` checkout 一個 `hotfix` 分支，修完後在 checkout 回 `master` 並 merge `hotfix`，同時也要再 checkout `develop` 分支，並 merge `hotfix` 讓 `develop` 能保有緊急修正的 code

參考資料： [Atlassian Gitflow Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
