---
layout: page
title: Team
permalink: /team/
subtitle: Who works on OpenEM?
tags: 
  - OpenEM team
  - Participating institutes
  - Swiss electron microscopy
  - Scientific collaboration
  - Research institutions
---

### Participating Institutes

<div class="institutes-content-container">
    <img src="/assets/img/opem_map.svg" alt="Map of participating institutions">
    <ul class="institutes-container">
        <li><a href="https://www.psi.ch">Paul Scherrer Institute (PSI)</a></li>
        <li><a href="https://www.epfl.ch">Swiss Federal Institute of Technology Lausanne (EPFL)</a></li>
        <li><a href="https://ethz.ch">Swiss Federal Institute of Technology in Zürich (ETHZ)</a></li>
        <li><a href="https://www.empa.ch/">Swiss Federal Laboratories for Materials Science and Technology (EMPA)</a></li>
        <li><a href="https://www.unibas.ch">University of Basel (UniBas)</a></li>
        <li><a href="https://www.unibe.ch/">University of Bern (UniBe)</a></li>
        <li><a href="https://unige.ch/">University of Geneva (UniGe)</a></li>
        <li><a href="#">University of Lausanne (UNIL)</a></li>
        <li><a href="https://www.uzh.ch/">University of Zurich (UZH)</a></li>
        <li><a href="https://www.dubochetcenter.ch/">Dubochet Center for Imaging (DCI)</a></li>
    </ul>
</div>

### Teams

<div class="text-center">
    {% for team in site.data.team %}
        <h2>{{ team.name }}</h2>
        <div class="subtitle">
            <div>{{ team.description.role }}</div>
            <div>{{ team.description.responsibility }}</div>
            <div>{{ team.description.affiliation }}</div>
            <br>
        </div>
        <ul class="team">
            {% for person in team.members %}
                <table>
                    <tr>
                        <td class="team-round-image">
                                <img
                                    src="/assets/img/team/{{ person.image }}"
                                    alt="{{ person.name }}"
                                />
                        </td>
                        <td class="team-top-aligned">
                            <b>
                                {% if person.page %}
                                <a href="{{ person.page }}">{{ person.name }}</a>
                                {% else %}
                                {{ person.name }}
                                {% endif %}
                            </b>
                            <div>{{ person.affiliation }}</div>
                            {% if person.position %}
                            <div>{{ person.position }}</div>
                            {% endif %}
                            <div>{{ person.wp }}</div>
                            <div><i>{{person.components}}</i></div>
                        </td>
                    </tr>
                </table>
            {% endfor %}
        </ul>
    {% endfor %}
</div>

<div class="text-center">
    {% for team in site.data.team-supporters %}
        <h2>{{ team.name }}</h2>
        <div class="subtitle">
            <div>{{ team.description.role }}</div>
            <div>{{ team.description.responsibility }}</div>
            <div>{{ team.description.affiliation }}</div>
            <br>
        </div>
        {% assign member_count = team.members | size %}
        {% for person in team.members %}
            {{ person.name }}{% if forloop.index < member_count %}, {% endif %}
        {% endfor %}
    {% endfor %}
</div>
