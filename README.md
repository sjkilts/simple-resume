simple html resume using markdown, liquid and yml
---

# resume.md
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

# resume.yml
	---
	- name: Name
	  email:  thisis@my.email
	  github: github username 
	
	  employment:
	  - employer:  a company
	    title:  your job
	    date:  2014-Present
	    description: this is what we worked on
	
	  - employer:  that company 
	    title:  worker
	    date:  2017-Present
	    description:  this is where working is
	
	  education:  
	  - school:  University
	    field: Learning
	    degree:  Certificate
	    year:  '2013'
	
	  - school:  School
	    field: Books
	    degree:  AD
	    year:  '2011'
	
	  skills:
	  - skill: Illustration
	    icon:  /img/icon.png
	    
	  - skill: UI/UX
	    icon:  /img/ui_ux-icon.png
	
	  - skill: Design
	    icon:  /img/design-icon.png
	
	  - skill: Strategy
	    icon:  /img/strategy-icon.png
	
	  highlight:  highlight your skill here
	
	  tools: >
	          some, things. for,
	            working, with
	
	  interests: >
	              learning, to, learn,        
	                 about learning learned,      
	                    people, about, learning
