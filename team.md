---
title: RoViT Team
permalink: /team/
---

{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|postdoc|gradstudent|visiting|others|alumni" | split: "|" %}

{% for item in people_array %}	

<div class="pos_header">
{% if item == 'postdoc' %}
	<h3>Postdoctoral Fellows</h3>
 {% elsif item == 'pi' %}
	<h3>Principal Investigator</h3>
 {% elsif item == 'gradstudent' %}
	<h3>Graduate Students</h3>	
 {% elsif item == 'alumni' %}
	<h3>Alumni</h3>
 {% else %}
	</div>
	{% continue %}
{% endif %}

</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people" style="width:100%">
      <p class="list-post-title">
        {% if profile.avatar %}
			<a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="{{site.baseurl}}/images/people/{{profile.avatar}}" style="float:left;margin:0 20px 20px 0;"></a>
        {% else %}
			<a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg" style="float:left;margin:0 20px 20px 0;"></a>
        {% endif %}
        		
        
{% if profile.link_page %}
		<a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a><br>		
{% else %}
		<a class="name">{{ profile.name }}</a><br>		
{% endif %}
        
		<p>{{ profile.description}}</p>
<!--		Joined: {{profile.joined}}<br> -->

{% if profile.office %}
		<i class="fa fa-building"></i> office: {{profile.office}}, 
{% endif %}
{% if profile.google_scholar %}
		<i class="fa fa-bar-chart"></i><a href="{{profile.google_scholar}}"> google scholar</a>, 
{% endif %}
{% if profile.github %}
		<i class="fa fa-github"></i><a href="https://github.com/{{profile.github}}"> github</a>, 
{% endif %}
{% if profile.twitter %}
		<i class="fa fa-twitter"></i><a href="https://twitter.com/{{profile.twitter}}"> twitter</a><br>
{% endif %}

<!--		<i class="fa fa-futbol-o"></i> kaggle](https://www.kaggle.com/hugoguh) <br> -->
				
      </p>
    </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>

{% endfor %}
