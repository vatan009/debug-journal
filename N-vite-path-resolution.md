# Vite Path Resolution Error
Node.js v22.14.0 PS D:\react_course\allsections\section10-Context_API_&_useReducer> npm run dev > context@0.0.0 dev > vite '_useReducer\node_modules\.bin\' is not recognized as an internal or external command, operable program or batch file. node:internal/modules/cjs/loader:1228 throw err; ^ Error: Cannot find module 'D:\react_course\allsections\vite\bin\vite.js' at Function._resolveFilename (node:internal/modules/cjs/loader:1225:15) at Function._load (node:internal/modules/cjs/loader:1055:27) at TracingChannel.traceSync (node:diagnostics_channel:322:14) at wrapModuleLoad (node:internal/modules/cjs/loader:220:24) at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:170:5) at node:internal/main/run_main_module:36:49 { code: 'MODULE_NOT_FOUND', requireStack: [] } Node.js v22.14.0
## Problem
`npm run dev` failed and Vite could not locate `vite.js`.

Error included:
- `MODULE_NOT_FOUND`
- `'_useReducer\node_modules\.bin\' is not recognized`

## Cause
The project directory name contained the special character `&`.

PowerShell treated `&` as a special operator, which corrupted the path parsing for Vite and Node.js.

Directory:
section10-Context_API_&_useReducer

## Fix
Renamed the directory to remove `&`.

npm run dev

## Lesson
Avoid special characters like:
& % ^ @ !

in project folder names because shells and build tools may interpret them differently and break path resolution.
