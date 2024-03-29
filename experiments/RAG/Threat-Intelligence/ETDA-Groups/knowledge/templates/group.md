# Threat actor: {{metadata['actor']}}

**UUID**: {{metadata['uuid']}}

**First seen**: {{metadata['first-seen']}}

**Source last modified**: {{metadata['last-card-change']}}

## Threat actor aliases

{% for alias in metadata['names'] %}{{alias['name']}} ({{alias['name-giver']}}){% if not loop.last %}, {% endif %}{% endfor %}

## Description

{{metadata['description']}}

## Sponsor type and motivation

**Sponsor**: {{metadata['sponsor']}}

**Motivation**: {% for motivation in metadata['motivation'] %}{{motivation}}{% if not loop.last %}, {% endif %}{% endfor %}


## Country of origin

{% for country in metadata['country'] %}{{country}}{% if not loop.last %}, {% endif %}{% endfor %}

## Observed attacked sectors where victims operate in

{% for sector in metadata['observed-sectors'] %}{{sector}}{% if not loop.last %}, {% endif %}{% endfor %}

## Observed attacked countries where victims operate in

{% for country in metadata['observed-countries'] %}{{country}}{% if not loop.last %}, {% endif %}{% endfor %}

## Observed usage of tools

{% for tool in metadata['tools'] %}{{tool}}{% if not loop.last %}, {% endif %}{% endfor %}

## Reported hacking operations

{% for operation in metadata['operations'] %}{{operation['date']}}: {{operation['activity']}}{% if not loop.last %}

{% endif %}{% endfor %}

## Reported counter operations against threat actor

{% for operation in metadata['counter-operations'] %}{{operation['date']}}: {{operation['activity']}}{% if not loop.last %}

{% endif %}{% endfor %}




