---
layout: page
title: Participants
permalink: /participants/
---

<style>

.part-name {
	font-size: 1.2rem;
	color: #000099;
}

.floating-box {
    width: 100%;
    padding-left:5px;
    padding-right:5px;
    padding-top:5px;
    padding-bottom:5px;
    border: 1px solid; 
    overflow: hidden;
    position: relative;
}

.floating-box:hover{
  background:#cccccc;
}

.bio {
	float: left;
    top: 0;
    bottom: 0;
    height: 100%;
    padding-left: 1%;
    padding-right: 5px;
    max-width: 78%;
    font-size: 0.8em;
    margins: auto;
    vertical-align: middle;
}

.photo {
	float: right;
	height: 100%;
	width: 18%;
}

h1:after
{
    content:' ';
    display:block;
    border:2px solid black;
}

h2:after
{
    content:' ';
    display:block;
    border:1px solid black;
}



</style>

The PCMIP meeting would not be possible without the contributions of the project participants.  The second PCMIP meeting includes the following individuals:

{% for participant in site.data.persons %}
<div class="floating-box">
	<div class="bio">
		<b class="part-name">{{participant.name}}</b>
		{% if participant.orcid %}
		<small>ORCID: <a href="https://orcid.org/{{participant.orcid}}">{{participant.orcid}}</a></small>
		{% endif %}
		{% if participant.website and participant.orcid %} -- {% endif %}
		{% if participant.website %}
		<small><a href="{{participant.website}}">Personal Website</a></small>
		{% endif %}
		<br>
		<b>{{participant.institution}}</b><br>
		{{participant.bio}}
	</div>
	<div class="photo">
		{% if participant.head %}
		<img src="{{participant.head}}">
		{% endif %}
	</div>
</div>

{% endfor %}
