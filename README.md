# scirex-annotation-for-s2orc
Each file contains one document per line in format  - 

```python
{
    "doc_id" : str = Document Id as used by Semantic Scholar,
    "words" : List[str] = List of words in the document,
    "sentences" : List[Span] = Spans indexing into words array that indicate sentences,
    "sections" : List[Span] = Spans indexing into words array that indicate sections,
    "ner" : List[TypedMention] = Typed Spans indexing into words indicating mentions ,
    "coref" : Dict[EntityName, List[Span]] = Salient Entities in the document and mentions belonging to it,
    "n_ary_relations" : List[Dict[EntityType, EntityName]] = List of Relations where each Relation is a dictionary with 5 keys (Method, Metric, Task, Material, Score),
    "method_subrelations" : Dict[EntityName, List[Tuple[Span, SubEntityName]]] = Each Methods may be subdivided into simpler submethods and Submenthods in coref array. For example, DLDL+VGG-Face is broken into two methods DLDL , VGG-Face.
}

Span = Tuple[int, int] # Inclusive start and Exclusive end index
TypedMention = Tuple[int, int, EntityType]
EntityType = Union["Method", "Metric", "Task", "Material"]
EntityName = str
```
