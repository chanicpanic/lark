Working with the SPPF
=====================

When parsing with earley, Lark provides the ``ambiguity='forest'`` option
to obtain the shared packed parse forest (SPPF) produced by the parser as 
opposed to it being automatically converted to a tree.

Lark provides a few tools to facilitate working with the SPPF. However, it
remains no simple undertaking. Here are some things to consider
when deciding whether using the SPPF is right for you.

**Pros**

- Efficient storage of highly ambiguous parses
- Precise handling of ambiguities
- Custom rule prioritizers
- Ability to handle infinite ambiguities
- Directly transform forest -> object instead of forest -> tree -> object

**Cons**

- More complex than working with a tree.
- SPPF may contain nodes corresponding to rules generated internally.
- Loss of Lark grammar features:

  - Rules starting with '_' are not inlined in the SPPF
  - Rules starting with '?' are never inlined in the SPPF
  - All tokens will appear in the SPPF

SymbolNode
----------

.. autoclass:: lark.parsers.earley_forest.SymbolNode

PackedNode
----------

.. autoclass:: lark.parsers.earley_forest.PackedNode

ForestVisitor
-------------

.. autoclass:: lark.parsers.earley_forest.ForestVisitor

ForestTransformer
-----------------

.. autoclass:: lark.parsers.earley_forest.ForestTransformer

TreeForestTransformer
---------------------

.. autoclass:: lark.parsers.earley_forest.TreeForestTransformer

handles_ambiguity
-----------------

.. autofunction:: lark.parsers.earley_forest.handles_ambiguity
