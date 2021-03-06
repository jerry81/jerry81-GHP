[Go Home](../index.md)

## Agent

datadog agent:  lightweight sw installed on host
  
host: the machine running the agent.  could be a containerzied host (guess we are using this)

sends metrics, events from host using integrations, DogStatsD, or the API (all datadog topics)

logs and traces also available

configured using datadog.yaml

config options passed with env variables 
e.g. DD_API_KEY

core checks: cpu, disk,  io, memory, network, uptime
docker ?, file handle (?),load?, 
ntp - network time protocol
, winproc?

events sent by agent: datadog.agent.up
datadog.agent.check_status

commands available to start, restart, stop agent 

agent may run on host, docker, or kubernetes 

agent is open source

## Integrations

can integrate with prometheus and openmetrics 

custom integrations done through datadog API

for kubernetes integration, container integration is recommended.  the agent runs inside a pod. cannot monitor starting phase of cluster 

1.  rights need to be given to the datadog agent running on pod
can be done by using kubectrl create then adding ACL files on github

2.  manifest file created 
run kubectrl create <path to manifest file>
  
3.  verify running with kubectl get daemonset

4.  enable log collection:  dd_logs_enabled

## API

access dd programatically through the api 
rest api

API key used for authentication
apis to 
create dashboards
slack integration
send logs thru http

## Monitors

all machines show up in Infrastructure page 

logback - successor to log4j 
hikaricp - jdbc connection pool - means connections are reused

infrastructure list to check if monitoring is enabled 
we have 6 hosts there, upon inspecting, we can see a default dashboard 

3 dd agents per kubernetes cluster (s & p)

containers tab lists all containers

## Vocabulary 
flannel:  network fabric often used with kubernetes 

rss memory: resident set size memory 

TX: transmit 

RX: receive 

helm: package manager for k8s 

RBAC: role based access control 

## Misc Learning

echo -n <non-base64-key> | base64 

