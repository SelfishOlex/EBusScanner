# EBusScanner
Scans your source code for Lumberyard EBuses and their use. Builds a digraph out of that information.

## Usage

```
EBus_Scanner.exe output.dot.txt C:\work\Lumberyard\dev\Gems\LightningArc
```

## Result

Produces a graphviz dot file, for example:

``` dot
digraph { 
    AssetCatalogRequestBus [shape=box,style=filled,color=".7 .3 1.0"] ;
    EditorLightningComponent -> AssetCatalogRequestBus;
    AudioRtpcComponentRequestBus [shape=box,style=filled,color=".7 .3 1.0"] ;
    LightningComponent -> AudioRtpcComponentRequestBus;
    AudioTriggerComponentRequestBus [shape=box,style=filled,color=".7 .3 1.0"] ;
    LightningComponent -> AudioTriggerComponentRequestBus;
    ComponentApplicationBus [shape=box,style=filled,color=".7 .3 1.0"] ;
    LightningComponent -> ComponentApplicationBus;
    ...
}
```

Then you can install graphviz and generate a graph like this:

```
"C:\Program Files (x86)\Graphviz2.38\bin\dot.exe" -Tpng output.dot.txt -o output.png
```

![alt text](https://github.com/Aristo7/EBusScanner/blob/master/example_graph.png)


## Notes

Requires C++17 (for std::filesystem)
