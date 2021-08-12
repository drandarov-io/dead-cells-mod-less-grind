# Changes 

## Cells
Cell Drops -> 5x / 10x

## Daily Run
Rewards -> After 1, 2 and 3 runs

## Blueprints
Common -> 20%
Uncommon -> 10%
Rare -> 5%
Legendary -> 2.5%

# Workflow (notes for myself):
.\PAKTool.exe -Expand -OutDir "export" -RefPak "..\res.pak"
.\CDBTool.exe -Expand -OutDir "export\data.cdb_" -RefCDB "export\data.cdb"

## Make changes

.\CDBTool.exe -Collapse -InDir "export\data.cdb_" -OutCDB "export\data.cdb"
rmdir /s export\data.cdb_
.\PAKTool.exe -CreateDiffPak -RefPak "..\res.pak" -InDir "W:\Games\SteamLibrary\steamapps\common\Dead Cells\ModTools\export" -OutPak ".\mod\res.pak"

## Testing
.\PAKTool.exe -Expand -OutDir "mod\test" -RefPak "mod\res.pak"