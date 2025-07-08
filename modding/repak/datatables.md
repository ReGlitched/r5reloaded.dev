# DataTables

### DTBL Assets

This asset type is used to define CSV format data tables within the .rpak. Data tables can be used to configure and store structured data like weapon stats, loot tables, or other game-related information. Can be referenced within the scripts to manage various gameplay elements.

We recommend structuring your CSV files with proper headers to ensure they are interpreted correctly by the game. A broken datatable can cause crashes.

```
{
    "_type": "dtbl",
    "_path": "datatable/(datatable path).rpak"
}
```
