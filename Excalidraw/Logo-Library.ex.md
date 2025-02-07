---
excalidraw-plugin: parsed
excalidraw-onload-script: "const FILENAME_FILTER = /^logo -/i;const KEYWORD_GRABBER = /(?:logo -)?([^-]*)-?/i;const COLS = 7;const LOCK_ICONS = false;const HEIGHT = 180;const WIDTH = 180;const TEXTHEIGHT = 40;const PADDING = 50;const api = ea.getExcalidrawAPI();const f = ea.targetView.file;const { zenModeEnabled, linkOpacity, trayModeEnabled, penMode, penDetected, allowPinchZoom, allowWheelZoom, pinnedScripts, customPens, zoom} = api.getAppState();api.resetScene();api.updateScene({ appState: { zenModeEnabled, linkOpacity, trayModeEnabled, penMode, penDetected, allowPinchZoom, allowWheelZoom, pinnedScripts, customPens, zoom }});const promisePool = async (tasks, concurrency, taskHandler) => { const results = []; const executing = []; for (const task of tasks) { const p = Promise.resolve().then(() => taskHandler(task)); results.push(p); if (concurrency <= tasks.length) { const e = p.then(() => executing.splice(executing.indexOf(e), 1)); executing.push(e); if (executing.length >= concurrency) { await Promise.race(executing); } } } return Promise.all(results);};const processIcon = async (task) => { const row = task.row; const rowOfIcons = task.icons; const eaTemp = ea.getAPI(ea.targetView); for (let col=0;col<rowOfIcons.length;col++) { const icon = rowOfIcons[col]; const id = await eaTemp.addImage(col * (WIDTH + PADDING), row * (HEIGHT + PADDING + TEXTHEIGHT), icon); if (f !== eaTemp.targetView.file && eaTemp.targetView?.getViewType?.() !== 'excalidraw') continue; if (!id) continue; const keywords = icon.basename.match(KEYWORD_GRABBER)[1].trim(); eaTemp.style.verticalAlign = 'top'; eaTemp.style.textAlign = 'center'; eaTemp.style.fontSize = 12; const el = eaTemp.getElement(id); let ratio = el.width / WIDTH; if (el.height / ratio > HEIGHT) ratio = el.height / HEIGHT; el.width = el.width / ratio; el.height = el.height / ratio; el.locked = LOCK_ICONS; eaTemp.style.strokeColor = 'black'; const labelID = eaTemp.addText(col * (WIDTH + PADDING) - PADDING / 2 + 10, row * (HEIGHT + PADDING + TEXTHEIGHT) + HEIGHT + PADDING / 2 - 10, keywords, { width: WIDTH + PADDING - 20, height: TEXTHEIGHT - 20, textAlign: 'center', textVerticalAlign: 'top', autoResize: false, }); eaTemp.getElement(labelID).locked = LOCK_ICONS; } await eaTemp.addElementsToView(false, false, false); eaTemp.targetView.clearDirty(); eaTemp.destroy();};const icons = app.vault.getFiles() .filter(f => (f.extension !== 'md' || ea.isExcalidrawFile(f)) && f.basename.toLowerCase().match(FILENAME_FILTER)) .sort((a, b) => a.basename.toLowerCase() < b.basename.toLowerCase() ? -1 : 1);const numRows = Math.ceil(icons.length / COLS);const iconsInRows = [];for (let i = 0; i < numRows; i++) { iconsInRows.push({icons: icons.slice(i * COLS, (i + 1) * COLS), row:i});};const concurrency = 3;await promisePool(iconsInRows, concurrency, processIcon);ea.targetView.clearDirty();api.zoomToFit();api.updateContainerSize(ea.getViewElements().filter(el => el.type === 'rectangle'));"
created: 2024-12-08T06:07
updated: 2024-12-08T06:10
---
#exclude 
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'


# Excalidraw Data
## Text Elements
anki ^6ZHZZgH2

apple ^5e7haqrG

arch ^SYtLjsES

bloodhound ^ZAgRrDEz

## Embedded Files
8a4aa889f202c0092355f3eff8494c9ba812a002: [[logo - anki.png]]

1e31e8a6e874535ce7c3f061db6b0792d603ea0d: [[logo - apple - Roundicons.png]]

6df9eb671c90d7be5d4ef556e2f9f6c5fed643a9: [[logo - arch - Archlinux.svg]]

d8b34076646755f2eaf327e941366c9b9f5ef2f0: [[logo - bloodhound - specterops.svg]]

%%
## Drawing
```compressed-json
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
```
%%