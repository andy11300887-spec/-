# GitHub Pages部署說明｜旅日手帖

本專案已準備好`docs/`發布資料夾（成果首頁、12頁互動簡報、Wiki可讀網頁、Graph流程與證據）。**本地通過驗證不等於已上線**；上線需要有GitHub帳號的權限。

## 建議方式：GitHub Desktop（Windows）

1. 解壓縮完整專案ZIP，保留`.git`資料夾。
2. 登入GitHub Desktop（https://desktop.github.com/）。
3. 選單`File → Add local repository... → Choose...`，選取`Japan-Travel-LLM-Wiki_v1`資料夾（內含`.git`）。
4. 點選`Publish repository`，名稱建議`japan-travel-llm-wiki`，並依GitHub Pages方案選擇適當公開權限。請先確認公開專案內容可以分享。
5. 在GitHub網站開啟該Repository，點選`Settings → Pages`。
6. `Build and deployment → Source`選擇`Deploy from a branch`。
7. `Branch`選擇本專案的`master`，資料夾選擇`/docs`，按`Save`。若發布成`main`分支，則改選`main`。
8. 等GitHub顯示實際部署成功的網址，再點開網站核對六項成果連結、12頁切換與互動功能。

網址會依你的GitHub使用者名稱與儲存庫名稱而定。不要自行假設已上線。

## 首頁與教學簡報

- 首頁網址格式：`https://<GitHub使用者名稱>.github.io/<儲存庫名稱>/`
- 簡報網址格式：`https://<GitHub使用者名稱>.github.io/<儲存庫名稱>/slides/deck.html`
- Wiki索引網址格式：`https://<GitHub使用者名稱>.github.io/<儲存庫名稱>/wiki/index.html`

## 後續更新

修改正式Wiki/HTML後，若需要同步發布文件，可在專案根目錄執行：

```bash
python -m pip install mistune
python tools/build_pages.py
python tests/check_pages_build.py
```

使用GitHub Desktop將新增的`docs/`提交並`Push origin`。GitHub Pages會依已設定的發布來源更新。

## 注意

- `/docs/.nojekyll`確保檔案直接按靜態內容發佈；網站不需要後端服務或API金鑰。
- `docs/`是公開網頁用的輸出，**GitHub儲存庫本身的可見性另由你決定**。公開上傳前請確認沒有個資、API金鑰、私人文件。
- 本地Markdown測試結果不同於實際GitHub Pages公開連結驗收；最後應以線上網站為準。
