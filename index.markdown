---
layout: default
---

{% for resume in site.data.resume %}

# {{ resume.name }}

[{{ resume.email }}](mailto:{{ site.email }})  
[github.com/{{ resume.github }}](https://github.com/{{ resume.github }}) 


## employment

{% for employer in resume.employment %}
- **{{ employer.employer }}** {{ employer.title }} *({{ employer.date }})*  
{{ employer.description }}
{% endfor %}

## education

<p>
{% for school in resume.education %}
	<strong>{{ school.field }}</strong> {{ school.school }} <em>({{ school.degree }}, {{ school.year }})</em><br>
{% endfor %}
</p>

## skills

<div>
{% for skill in resume.skills %}
	<div>  
		<span>{{ skill.skill }}</span>
	</div>
{% endfor %}
</div>

- {{ resume.highlight }}

## tools

{{ resume.tools }}

## interests

{{ resume.interests }}

{% endfor %}
