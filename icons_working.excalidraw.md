---
excalidraw-plugin: parsed
excalidraw-onload-script: "const FILENAME_FILTER = /^icon -/i;const KEYWORD_GRABBER = /(?:icon -)?([^-]*)-?/i;const COLS = 7;const LOCK_ICONS = false;const HEIGHT = 180;const WIDTH = 180;const TEXTHEIGHT = 40;const PADDING = 50;const api = ea.getExcalidrawAPI();const f = ea.targetView.file;const { zenModeEnabled, linkOpacity, trayModeEnabled, penMode, penDetected, allowPinchZoom, allowWheelZoom, pinnedScripts, customPens, zoom} = api.getAppState();api.resetScene();api.updateScene({ appState: { zenModeEnabled, linkOpacity, trayModeEnabled, penMode, penDetected, allowPinchZoom, allowWheelZoom, pinnedScripts, customPens, zoom }});const promisePool = async (tasks, concurrency, taskHandler) => { const results = []; const executing = []; for (const task of tasks) { const p = Promise.resolve().then(() => taskHandler(task)); results.push(p); if (concurrency <= tasks.length) { const e = p.then(() => executing.splice(executing.indexOf(e), 1)); executing.push(e); if (executing.length >= concurrency) { await Promise.race(executing); } } } return Promise.all(results);};const processIcon = async (task) => { const row = task.row; const rowOfIcons = task.icons; const eaTemp = ea.getAPI(ea.targetView); for (let col=0;col<rowOfIcons.length;col++) { const icon = rowOfIcons[col]; const id = await eaTemp.addImage(col * (WIDTH + PADDING), row * (HEIGHT + PADDING + TEXTHEIGHT), icon); if (f !== eaTemp.targetView.file && eaTemp.targetView?.getViewType?.() !== 'excalidraw') continue; if (!id) continue; const keywords = icon.basename.match(KEYWORD_GRABBER)[1].trim(); eaTemp.style.verticalAlign = 'top'; eaTemp.style.textAlign = 'center'; eaTemp.style.fontSize = 12; const el = eaTemp.getElement(id); let ratio = el.width / WIDTH; if (el.height / ratio > HEIGHT) ratio = el.height / HEIGHT; el.width = el.width / ratio; el.height = el.height / ratio; el.locked = LOCK_ICONS; eaTemp.style.strokeColor = 'black'; const labelID = eaTemp.addText(col * (WIDTH + PADDING) - PADDING / 2 + 10, row * (HEIGHT + PADDING + TEXTHEIGHT) + HEIGHT + PADDING / 2 - 10, keywords, { width: WIDTH + PADDING - 20, height: TEXTHEIGHT - 20, textAlign: 'center', textVerticalAlign: 'top', autoResize: false, }); eaTemp.getElement(labelID).locked = LOCK_ICONS; } await eaTemp.addElementsToView(false, false, false); eaTemp.targetView.clearDirty(); eaTemp.destroy();};const icons = app.vault.getFiles() .filter(f => (f.extension !== 'md' || ea.isExcalidrawFile(f)) && f.basename.toLowerCase().match(FILENAME_FILTER)) .sort((a, b) => a.basename.toLowerCase() < b.basename.toLowerCase() ? -1 : 1);const numRows = Math.ceil(icons.length / COLS);const iconsInRows = [];for (let i = 0; i < numRows; i++) { iconsInRows.push({icons: icons.slice(i * COLS, (i + 1) * COLS), row:i});};const concurrency = 3;await promisePool(iconsInRows, concurrency, processIcon);ea.targetView.clearDirty();api.zoomToFit();api.updateContainerSize(ea.getViewElements().filter(el => el.type === 'rectangle'));"
---


%%
## Drawing
```compressed-json
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=
```
%%