# sphinx-c4
Brings the C4 model into sphinx

## Technology collection

* [C4 model](https://c4model.com/)
* [C4 Examnple viewer](https://c4model.com/diagrams/example)
  *   A dynamic viewer, which shows sub-architectures via click on system-elements.
  *   Great, as it is a single "image", but provides so many interactive views
* [Diagram-as-code C4 support](https://diagrams.mingrammer.com/docs/nodes/c4)
  * Looks a little limited and the graphical representations are not 100% in sync or even available, like the mobile Component or person
* [Structurizr JS Viewer](https://github.com/structurizr/ui)
  * Used for the above example
  * MIT license
* [pystructurizr: Python interface for the structurizer JSON format](https://github.com/nielsvanspauwen/pystructurizr)
  * Could be used to generate the json and use the `ui` to show it

Structurizer DSL online editor: https://structurizr.com/dsl

## Assumptions

* We document the system, container, component level only.
* Documenting/Design the code architecture itself is not a topic
  * This is also often not done by teams, as the code is the truth
  *  The smallest code artifact, which can be checked against the architecture is the "SW Component"
  *  If more sw architecture is needed, another extension for SysML and other formats may be needed




## Tasks

### Keep it simple
This way just generates the C4 image for C4-Elements and views.
No export to an architecture-as-code DSL or other new tooling.

1. Define Sphinx-Needs types, options and links to represent C4 elements
   * System, Container, Component (Standard C4 elements)
   * Landscape/Diagram type or a `needc4` directive to describe the diagram to show on landscape view.
2. Use [Diagram-as-code C4 support](https://diagrams.mingrammer.com/docs/nodes/c4) to paint images for the related C4 elements
   * Not sure if this is a good idea because the lib lacks real C4 support

### Going the Structurizere way
This is creating a structurizer model out of the Sphinx-Needs model, so that other tools can use the outcome and e.g. generate images on the fly.
However, the support for this format is very limited in other tools and especially often not Open-Source.

1. Define Sphinx-Needs types, options and links to represent C4 elements
2. Create a `pystructurizr` model out of the Sphinx-Needs objects.
3. Use the needarch concept: A system defines the connections of imported containers
   * This is then also a c4 view
4. **TBD**: Provide ``needview`` to define a customc4-based view
