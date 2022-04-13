---
layout: default
title: Home
---
<!-- ========== BIO ========== -->
<div class="docs-section" id="bio">
  <h4>Bio</h4>
  <p>
  I am a senior undergraduate at at School of Mechatronical Engineering at Beijing Institute of Technology. My research interest is in computer vision,natural language processing and robotics control. 
  My recent work has focused on obejct detection on UAVs.
  My research often falls at the application of Computer Vision, Machine Learning.
  </p>

  <p>
  I am currently a research assistant at School of Mechatronical Engineering, supervised by Prof. <a href="https://smen.bit.edu.cn/sztd/szms/tcykzgcx/b162094.htm" target="_blank">Yushu Yu</a>.
  I have also worked with Prof. <a href="https://people.engr.ncsu.edu/mshahza/" target="_blank">Muhammad Shahzad</a> in 2021 summer. In 2022 fall....
  </p> 
  <!--
  I am a Postdoc at the department of Management Science and Engineering at Stanford University, working with <a href="https://web.stanford.edu/~jugander/" target="_blank">Johan Ugander</a>. 
  My research develops tools for analyzing large-scale social data, aiming to provide a better understanding of social structure and behaviors online while also impacting the design of digital social systems.
  My work often falls at the intersections of Social Networks, Machine Learning, and Causal Inference.
  </p>

  <!-- <p>
  I completed my Ph.D. from MIT in 2020 under the supervision of Deb Roy. 
  Before coming to MIT, I spent one year in Paris and one year in Barcelona doing a M.Sc. in Data mining and Knowledge Management. 
  I got my B.Sc. from Staffordshire University with First Class honors in Computer Science. 
  Throughout my graduate studies, I spent several summers doing internships in industry, including Yahoo! Labs, Amazon, LinkedIn, and Facebook.
  </p> -->
  
</div>


<!-- ========== PUBLICATIONS ========== -->
<div class="docs-section" id="publications">
  <h4>Publications</h4>

  <p>Most recent publications on <a href="https://scholar.google.com/citations?view_op=list_works&hl=en&user=WMa5iIUAAAAJ" target="_blank">Google Scholar</a>.<br/>
  <sup>‡</sup> indicates equal contribution.
  </p>

  <ul class="tab-nav">
    <li><div class="button active" data-ref="#papers-selected">Selected</div></li>
    <li><div class="button" data-ref="#papers-all">All</div></li>
  </ul>

  <div class="tab-content">
    <div class="tab-pane active" id="papers-selected">
      {% assign selected_papers = site.data.publications.papers | where: "selected", "y" %}
      {% for paper in selected_papers %}
        <div class="paper">
          <p class="title"><b>{{ paper.title }}</b></p>
          <p>{{ paper.authors }}</p>
          <p><i>{{ paper.venue }}</i></p>
           <div class="paper-buttons">
            {% if paper.paper_pdf %}
              <a class="button" href="{{ paper.paper_pdf | prepend: site.baseurl }}" target="_blank">Paper</a>
            {% endif %}

          </div>
        </div>
      {% endfor %}
    </div>

    <div class="tab-pane" id="papers-all">
      {% for paper in site.data.publications.papers %}
        <div class="paper">
          <p class="title"><b>{{ paper.title }}</b></p>
          <p>{{ paper.authors }}</p>
          <p><i>{{ paper.venue }}</i></p>
           <div class="paper-buttons">
            {% if paper.paper_pdf %}
              <a class="button" href="{{ paper.paper_pdf | prepend: site.baseurl }}" target="_blank">Paper</a>
            {% endif %}

            {% if paper.slides %}
              <a class="button" href="{{ paper.slides | prepend: site.baseurl }}" target="_blank">Slides</a>
            {% endif %}

            {% if paper.poster %}
              <a class="button" href="{{ paper.poster | prepend: site.baseurl }}" target="_blank">Poster</a>
            {% endif %}

            {% if paper.video %}
              <a class="button" href="{{ paper.video }}" target="_blank">Video</a>
            {% endif %}

            {% if paper.code %}
              <a class="button" href="{{ paper.code }}" target="_blank">Code</a>
            {% endif %}

            {% if paper.data %}
              <a class="button" href="{{ paper.data }}" target="_blank">Data</a>
            {% endif %}

          </div>
        </div>
      {% endfor %}
    </div>
  </div>
</div>

 <!-- ========== PROJECTS ==========  -->
<div class="docs-section" id="projects">
  <h4>Projects</h4>

  <ul class="tab-nav">
    <li><div class="button active" data-ref="#projects-selected">Selected</div></li>
    <li><div class="button" data-ref="#projects-all">All</div></li>
  </ul>

  <div class="tab-content">
    <div class="tab-pane active" id="projects-selected">
      {% assign selected_projects = site.data.projects.projects | where: "selected", "y" %}
      {% for project in selected_projects %}
        {% assign index_modulo = forloop.index0 | modulo:3 %}
        {% if index_modulo == 0 %}
          <div class="row">
        {% endif %}

          <div class="four columns">
            <div class="project-container">

                <!-- <div class="project-image-container">
                  <a href="{{ project.url }}">
                    <img src="{{ project.thumbnail }}" class="u-max-full-width" />
                  </a>
                </div> -->

                <div class="project-caption">
                  <b>{{ project.title }}</b> <br/>
                  {{ project.subtitle }}
                </div>

            </div>
          </div>

        {% if index_modulo == 2 %}
          </div>
        {% endif %}
      {% endfor %}
    </div>

    <div class="tab-pane" id="projects-all">
      {% for project in site.data.projects.projects %}
        {% assign index_modulo = forloop.index0 | modulo:3 %}
        {% if index_modulo == 0 %}
          <div class="row">
        {% endif %}

          <div class="four columns">
            <div class="project-container">

                <!-- <div class="project-image-container">
                  <a href="{{ project.url }}">
                    <img src="{{ project.thumbnail }}" class="u-max-full-width" />
                  </a>
                </div> -->

                <div class="project-caption">
                  <b>{{ project.title }}</b> <br/>
                  {{ project.subtitle }}
                </div>

            </div>
          </div>

        {% if index_modulo == 2 %}
          </div>
        {% endif %}
      {% endfor %}
    </div>
  </div>

</div>

<!-- ========== RESUME ========== -->
<div class="docs-section" id="resume">
  <h4>Vitæ</h4>

 <p>Full Resume in <a href={{ "/assets/cv/CV.pdf" | prepend: site.baseurl }} target="_blank">PDF</a>.</p>

  <!-- The Timeline -->
  <ul class="timeline">
    {% for exp in site.data.experience.experiences %}
    <li>
      {% if exp.category == "work" %}
      <div class="direction-l">
      {% else %}
      <div class="direction-r">
      {% endif %}
        <div class="flag-wrapper">
          <span class="flag">{{ exp.place }}</span>
          <span class="time-wrapper"><span class="time">{{ exp.time }}</span></span>
        </div>
        <div class="desc"><b>{{ exp.title }}</b> <br/> {{ exp.subtitle }}</div>
      </div>
    </li>
    {% endfor %}
  </ul>
</div>

<div class="docs-section">
<p>Thanks to <a href="https://web.stanford.edu/~msaveski/" target="_blank">Martin Saveski</a> for the website template.</p>
</div>
