---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
---

{% comment %}
Each of the sections below can be found in an individual markdown file.
This makes it easier for people to edit the contents in the UKRN Workshop Builder.
{% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% if site.eventbrite %}
**Some adblockers block the registration window. If you do not see the
  registration box below, please check your adblocker settings.**

<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{site.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% if site.topic == "open-data" %}
{% include intro/topic-intros/open-data.md %}
{% elsif site.topic == "open-code" %}
{% include intro/topic-intros/open-code.md %}
{% elsif site.topic == "open-access" %}
{% include intro/topic-intros/open-access.md %}
{% elsif site.topic == "preregistration" %}
{% include intro/topic-intros/preregistration.md %}
{% elsif site.topic == "preprints" %}
{% include intro/topic-intros/preprints.md %}
{% else %}
{% include intro/topic-intros/unknown-topic.md %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% assign begin_address = site.address | slice: 0, 4 | downcase  %}
{% if site.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if site.latitude and site.longitude and online == "false" %}
<p id="where">
  <strong>Where:</strong>
  {{site.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{site.latitude}}&mlon={{site.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{site.latitude}},{{site.longitude}}">Google Maps</a>.
</p>
{% elsif online == "true_public" %}
<p id="where">
  <strong>Where:</strong>
  online at <a href="{{site.address}}">{{site.address}}</a>.
  If you need a password or other information to access the training,
  the instructor will pass it on to you before the workshop.
</p>
{% elsif online == "true_private" %}
<p id="where">
  <strong>Where:</strong> This training will take place online.
  The instructors will provide you with the information you will need to connect to this meeting.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if site.start_date %}
<p id="when">
  <strong>Dates:</strong>
  18, 20, 22, and 29 April 2022
</p>
<p>
  <strong>Time:</strong>
    9:00–10:15 (Pacific) = 11:00–12:15 (Central) = 12:00–13:15 (Eastern) = 18:00–19:15 (Europe)
</p>
<p>
  <strong>Calendar entries:</strong>
  <a href="https://drive.google.com/file/d/19fGGn9XhkRVOPYCzuZoXvqY-xiRukE3a/view?usp=sharing" target="_blank">Download iCal cor all four days</a>, or <br/>
  use World Time Buddy for
  <a href="https://www.worldtimebuddy.com/?qm=1&lid=2657896,5391959,5128581,4335045&h=2657896&date=2022-4-18&sln=18-19.5&hf=1" target="_blank">Day 1</a>,
  <a href="https://www.worldtimebuddy.com/?qm=1&lid=2657896,5391959,5128581,4335045&h=2657896&date=2022-4-20&sln=18-19.5&hf=1" target="_blank">Day 2</a>,
    <a href="https://www.worldtimebuddy.com/?qm=1&lid=2657896,5391959,5128581,4335045&h=2657896&date=2022-4-22&sln=18-19.5&hf=1" target="_blank">Day 3</a>, and
    <a href="https://www.worldtimebuddy.com/?qm=1&lid=2657896,5391959,5128581,4335045&h=2657896&date=2022-4-29&sln=18-19.5&hf=1" target="_blank">Day 4</a>. (Note: World Time Buddy supports 30-minute chunks, so the calendar entries download from there will be 15 minutes longer than the actual time.)
</p>


{% endif %}

{% comment %} Include the extra optional files listed in optional_intro_sections {% endcomment %}
{% for X in site.optional_intro_sections %}
{% include intro/optional/{{ X }}.md %}
{% endfor %}

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact:</strong>
  Please email the instructors for more information.
  {% if site.instructor_emails %}
    The instructors' emails are:
    <ul>
    {% for email in site.instructor_emails %}
      <li><a href='mailto:{{email}}'>{{email}}</a></li>
    {% endfor %}
    </ul>
  {% endif %}
</p>

<hr/>

{% comment %}
SCHEDULE

Show the workshop's schedule.

The schedule is automatically generated from the lessons in `./_episodes` and `./episodes_rmd`, which are in turn produced by the generator tool.
{% endcomment %}

<h2 id="schedule">Schedule</h2>

{% include schedule.html %}

<hr/>


<h2 id="setup">Setup</h2>
{% comment %}
SETUP

The setup page simply loops through the entries in site.setup_files and links them with available installation guides from _includes/install_instructions
{% endcomment %}
{% if site.setup_files.size > 0 %}
{% comment %}Sum up the times taken to install the software{% endcomment %}

To participate in a {{ site.title | capitalize }}
workshop,
you will need access to the software described below.
In addition, you will need an up-to-date web browser.

The Carpentries maintain a list of common issues that occur during installation as a reference for instructors
that may be useful on the
[Configuration Problems and Solutions wiki](https://github.com/carpentries/workshop-template/wiki/Configuration-Problems-and-Solutions).

{% include intro/_participant-setup.html %}
{% else %}
To participate in this workshop you will need an up-to-date web browser.
{% endif %}


<!--PADLET
{% if site.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ site.collaborative_notes }}">Padlet</a> for asking questions, commenting, sharing URLs, and bits of code.
</p>
<hr/>
{% endif %}
-->

<!--SURVEY
{% assign pre = site.pre_survey | size %}
{% assign post = site.post_survey | size %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the course.</p>
<p><a href="{{ site.pre_survey }}{{ site.workshop_id }}" target="_blank">Pre-course Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.workshop_id }}" target="_blank">Post-course Survey</a></p>
<hr/>
-->
