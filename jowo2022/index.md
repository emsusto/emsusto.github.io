## Ensusto 2022

Ensusto 2022 will take place at [JOWO 2022](https://www.iaoa.org/jowo/2022/index.html), which is held at Jönköping University August 15-19, 2022.
{# Here goes the navbar #}

{% for entry in site.data.navigation %}
{% capture fullurl %}{{ site.baseurl }}{{ entry.url }}{% endcapture %}
    {% if fullurl == page.url %}
        {% assign current_page = fullurl %}
        {% break %}
    {% elsif page.url contains fullurl %}
        {% assign current_page = fullurl %}
    {% endif %}
{% endfor %}

<!-- Then we build the nav bar. -->
<nav>
    <ul>
    {% for entry in site.data.navigation %}
        {% if entry.url == current_page %}
            {% assign current = ' class="current"' %}
        {% else %}
            <!-- We have to declare it 'null' to ensure it doesn't propagate. -->
            {% assign current = null %}
        {% endif %}
        {% assign sublinks = entry.sublinks %}
        {% if sublinks %}
        <li{{ current }}>
            <a href="{{ site.baseurl }}{{ entry.url }}">{{ entry.title }}</a>
            <ul>
                {% for sublink in sublinks %}
                <li><a href="{{ site.baseurl }}{{ sublink.url }}">{{ sublink.title }}</a></li>
                {% endfor %}
            </ul>
        </li>
        {% else %}
        <li{{ current }}><a href="{{ site.baseurl }}{{ entry.url }}">{{ entry.title }}</a></li>
        {% endif %}
    {% endfor %}
    </ul>
</nav>

{# Here ends the navbar #}

## About Ensusto

Energy, and sustainability more broadly, are increasingly relevant topics in the context of the climate crisis and a rapidly changing world, 
around which data and research needs to be aggregated. Topics that will be within scope of the proposed workshop include energy systems, 
sustainability, climate, ecosystems, and associated human socioeconomic impacts and preventative behaviours, including approaches to 
sustainable development. The workshop will focus on the development of ontologies for these domains as well as applications in which 
such ontologies are used.

## Scope

Papers in this track should be related to a novel ontology for the domain of energy and sustainability or systems and methods related to the creation,
evaluation or application of such ontologies or systems and methods that use such ontologies in a meaningful way. Publications that focus on a specific ontology must provide additional value that enables a reader to
understand the represented domain and specific design decisions. These publications should address the following points:

* A clear description of the domain and scope of the ontology or system
* Unique challenges and requirements that the domain and possible use-cases entail
* Methodologies and design choices that have been employed to address these challenges
* Potential applications

For system-focused submissions, the usage of an ontology in should exeed that of a mere taxonomy. These submissions should include a clear discussion
of the ways in which semantic properties of the ontology enhance the system and aid its intended use-cases. This includes, but is not limited to:

* Ontology-based data access or data management
* Symbolic AI
* Ontology creation, extension or testing

Review criteria: Reviews will consider the novelty, signidicance and soundness of the respective ontology or system regarding the points discussed above.


## Timeline

* Call for papers - March 16, 2022
* Submission deadline - June 3rd, 2022
* Notification date - July 15th, 2022
* Camera ready version due - August 5th, 2022
