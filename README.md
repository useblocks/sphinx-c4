# sphinx-c4
Brings the C4 model into sphinx

## Technology collection

* [C4 model](https://c4model.com/)
* [C4 Examnple viewer](https://c4model.com/diagrams/example)
  *   A dynamic viewer, which shows sub-architectures via click on system-elements.
  *   Great, as it is a single "image", but provides so many interactive views
* [Structurizr JS Viewer](https://github.com/structurizr/ui)
  * Used for the above example
  * MIT license
* [pystructurizr: Python interface for the structurizer JSON format](https://github.com/nielsvanspauwen/pystructurizr)
  * Could be used to generate the json and use the `ui` to show it

Structurizer DSL online editor: https://structurizr.com/dsl


## Tasks

1. Define Sphinx-Needs types, options and links to represent C4 elements
2. Create a `pystructurizr` model out of the Sphinx-Needs objects.
3. Use the needarch concept: A system defines the connections of imported containers
   * This is then also a c4 view
4. **TBD**: Provide ``needview`` to define a customc4-based view
