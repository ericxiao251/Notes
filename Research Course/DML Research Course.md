# How to get started

## People to contact...
* [Matthew Woolhouse](woolhouse@mcmaster.ca) - Professor
* [Jotthi Bansal](bansalj@mcmaster.ca) - Lab instructor
* [Kurt](kurtbradd@gmail.com) - Developer
* [Michael](baronemda@gmail.com) - Developer
* [Michael Mallon](mallonm@mcmaster.ca) - IT Specialist

## Server info
* Server ip address: `130.113.103.46`
* Server host: `user_name@woolhouse-g.humanities.mcmaster.ca`

## How to use the Humanities Servers
1. Get access to the Humanities Server, ask [Dr. Woolhouse](woolhouse@mcmaster.ca) or [Jotthi](bansalj@mcmaster.ca).
2. Install VPN ([link](http://www.mcmaster.ca/uts/network/vpn/)) to access the server without being connected to McMaster's network.
3. ssh into the server. `ssh user_name@woolhouse-g.humanities.mcmaster.ca`.
---

## Workflow of the web crawler

clone the repo.
get the credentials.
install mysql, redis.

### 1. Getting the GrailsUI
1. run `npm run development:master`
    * This initializes the dashboard and job queue.
2. go to dashboard --> [link](http://localhost:3001/)

    NTS: port listed in confs
3. run `seed:musicbrainz:track`  
    * This loads the queue with jobs taken from the seed files (tsv).
4. run `npm run development:worker`  
    * This plucks the jobs from the job queue and processes the jobs.
    * This also inserts into the database.
5. run `flushall`.
    * to clear redis database and to delete all the queued jobs.
