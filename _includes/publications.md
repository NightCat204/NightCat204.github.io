{% for section in site.data.publications.sections %}
<h2 id="{{ section.id }}" class="project-section-heading">{{ section.title }}</h2>

<div class="publications">
<ol class="bibliography">

{% for item in section.items %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if item.image %}
    <img src="{{ item.image }}" class="teaser img-fluid z-depth-1" alt="{{ item.title }}">
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title project-title-line">
        <span>{{ item.title }}</span>
      </div>
      <div class="author">{{ item.subtitle }}</div>
      <div class="periodical project-summary">{{ item.summary }}</div>
      {% if item.links or item.notes %}
      <div class="links project-links">
        {% if item.links %}
        {% for project_link in item.links %}
        <a href="{{ project_link.url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">{{ project_link.label }}</a>
        {% endfor %}
        {% endif %}
        {% if item.notes %}
        <span class="project-note">{{ item.notes }}</span>
        {% endif %}
      </div>
      {% endif %}
  </div>
</div>
</li>

{% endfor %}

</ol>
</div>
{% endfor %}
