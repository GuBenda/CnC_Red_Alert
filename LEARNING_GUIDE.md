# Learning the Command & Conquer: Red Alert Source Code

This repository is a copy of Electronic Arts’ public **Command & Conquer: Red Alert** source-code release. The official README describes it as source code for Red Alert and notes that the repository was released for preservation and Steam Workshop support.[1]

> Electronic Arts states that rebuilding the source requires legacy dependencies and tools, and that the current source does not fully compile without restoration work.[1]

## How to use this repository in VS Code

Open the repository folder in **Visual Studio Code** and treat it first as a code-reading project rather than a modern buildable C++ project. The included `.vscode/settings.json` file disables noisy C++ error squiggles and helps VS Code recognize the legacy uppercase file extensions used throughout the codebase.

| Goal | VS Code command | Why it helps |
|---|---:|---|
| Open a specific file quickly | `Ctrl+P` or `Cmd+P` | Jump to files such as `CODE/UNIT.CPP` or `CODE/HOUSE.CPP` without browsing folders manually. |
| Search the whole codebase | `Ctrl+Shift+F` or `Cmd+Shift+F` | Find class names, gameplay terms, and function calls across hundreds of files. |
| See symbols in one file | `Ctrl+Shift+O` or `Cmd+Shift+O` | Navigate large files such as `CODE/CONQUER.CPP`. |
| Jump to a definition | `F12` | Move from a function or class reference to its implementation or declaration. |
| Find references | `Shift+F12` | Learn who calls a function and how data flows through the game. |

## Repository map

The most important folder for learning the game itself is `CODE/`. Other folders are support libraries, tools, video/audio-related systems, old networking code, and launcher-related programs.

| Folder | Main purpose |
|---|---|
| `CODE/` | Main Red Alert game source: gameplay, objects, units, houses, scenarios, map, UI, networking, and rules. |
| `IPX/` | Legacy IPX/network-related code. |
| `LAUNCH/` and `LAUNCHER/` | Launcher-related files and program code. |
| `TOOLS/` | Utility tools, including audio and MIX-file related tooling. |
| `VQ/` and `WINVQ/` | VQA/video-related code and viewers. |
| `WIN32LIB/` | Westwood Windows support code. |
| `WWFLAT32/` | Lower-level Westwood support code for graphics, memory, and miscellaneous utilities. |

## Best first files to read

A good first pass should focus on the main RTS concepts: objects, units, buildings, players, the map, scenarios, and rules. Do not start alphabetically; start with systems you already understand from playing strategy games.

| Topic | Files to open first | What to look for |
|---|---|---|
| Global project context | `README.md`, `LICENSE.md` | Release purpose, license, and build limitations. |
| Object hierarchy | `CODE/ABSTRACT.H`, `CODE/OBJECT.H`, `CODE/TECHNO.H`, `CODE/FOOT.H` | How the game represents things that exist in the world. |
| Vehicles | `CODE/UNIT.H`, `CODE/UNIT.CPP` | Unit state, movement, combat, targeting, and mission behavior. |
| Infantry | `CODE/INFANTRY.H`, `CODE/INFANTRY.CPP` | Soldier-specific behavior and how it differs from vehicles. |
| Buildings | `CODE/BUILDING.H`, `CODE/BUILDING.CPP` | Construction, ownership, production, damage, and structure logic. |
| Players/factions | `CODE/HOUSE.H`, `CODE/HOUSE.CPP` | Money, ownership, production, faction state, and player/AI logic. |
| Teams and AI | `CODE/TEAM.H`, `CODE/TEAM.CPP` | Group behavior, scripted team actions, and AI-style coordination. |
| Map and cells | `CODE/MAP.CPP`, `CODE/CELL.CPP`, `CODE/DISPLAY.H` | How the RTS map is represented and displayed. |
| Scenarios | `CODE/SCENARIO.CPP` | Mission/scenario loading and runtime setup. |
| Main orchestration | `CODE/CONQUER.CPP` | High-level game control and runtime flow. |

## First one-hour study plan

Spend the first hour building a mental model rather than trying to compile the code. The project comes from a legacy Win32/DOS-era C++ environment and uses historical dependencies, so immediate compilation is not the right first milestone.[1]

| Time | Activity | Output |
|---:|---|---|
| 10 minutes | Read `README.md` and skim `LICENSE.md`. | You understand that this is a preservation source release. |
| 10 minutes | Open `CODE/UNIT.H` and `CODE/UNIT.CPP`. | You can describe what a vehicle stores and does. |
| 10 minutes | Open `CODE/BUILDING.H` and `CODE/BUILDING.CPP`. | You can compare building behavior with unit behavior. |
| 10 minutes | Open `CODE/HOUSE.CPP`. | You can identify player/faction/economy concepts. |
| 10 minutes | Open `CODE/CELL.CPP` and `CODE/MAP.CPP`. | You can explain how the world grid begins to work. |
| 10 minutes | Search for `Damage`, `Target`, `Mission`, `Factory`, and `Scenario`. | You have a short list of functions you want to study next. |

## Search terms to try immediately

Use global search in VS Code for these terms:

```text
class UnitClass
class BuildingClass
class HouseClass
class TeamClass
class CellClass
Damage
Target
Mission
Scenario
Factory
AI
Move
Fire
```

When you find a function, ask three questions: **Which class owns this behavior? Who calls it? What state does it read or change?** Answering those three questions repeatedly is the fastest way to understand an unfamiliar game codebase.

## References

[1]: https://github.com/electronicarts/CnC_Red_Alert "Electronic Arts, CnC_Red_Alert GitHub repository"
