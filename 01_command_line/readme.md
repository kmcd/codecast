# Command line

## INTRO
  Pre-requisite knowledge

  ## What is UNIX / command line?

  http://c1.staticflickr.com/3/2323/2167070556_9bf42ec329_b.jpg

  * kernel
  * shell
  * proccesses

  ## What are commands ?

  https://www.flickr.com/photos/80901381@N04/7649502498
  https://www.flickr.com/photos/sagesolar/15388034734/in/photolist-prMGBG-78vb2H-9Vaf28-9sRYuo-73xQJY-8Zp6sD-73tV4x-73xTPS-73-73tTED-73tTzT-73tS26-73xQG3-73tPE2-73tPwn-73tPqR-73tPoe-73xNf1-73tNPc-73tHvg-73xGoU-73xGku-73xEny-73txGr-73xwwy-6JkGER-73xwrC-73txqX-4BygUB-6JkF8P

  An executable program
  Takes/accepts args
  Carries out action
  Returns 0 or more result(s)

  N.B. case sensitive
  N.B. no output

  ## File system

  * Hier
  * Files
  * Dirs
  * Root
  * Home

  1. Most useful commands

  (Moving around)
  pwd, ls, cd

  http://blog.teamtreehouse.com/introduction-to-the-mac-os-x-command-line
  https://developer.apple.com/library/mac/documentation/OpenSource/Conceptual/ShellScripting/CommandLInePrimer/CommandLine.html
  http://cli.learncodethehardway.org/book/

  https://www.flickr.com/photos/tasteful_tn/226000168/in/photolist-kYiYC-4Eu1S4-p9f6qM-vvU95h-4PRucd-9EVhyB-4A5uKR-rn188X-ny9smg-r1UnXb-3pCTXe-rNj5DS-ts1oSK-ow2386-hwhZjx-9DqkD-brnogF-wxW3PX-jEgYUf-hP1MxN-nskQHV-a411n8-8PXGoh-pUNKVi-ynfNNJ-nkxvmB-8WgkdU-xp7Dcq-sEk3Lv-4eCfzf-xfiiJE-gXv7QQ-qVmVzx-5CKVcG-7Zz4pe-eeSJSJ-eeBxiZ-kLoJy-a3v3xz-5gC7GZ-qaaU3R-oFPAn5-eyu4RF-7Q3bH2-6WmEs-q2hP-395Bw2-Dmw1V-6rq2m-r6WSjr
  https://www.flickr.com/photos/deanhochman/14779546027/in/photolist-4H9aYS-ntf64z-qbWXEQ-ou5LTx-rn188X-kYiYC-ow2386-hP1MxN-a411n8-qVmVzx-kLoJy-oFPAn5-q2hP-395Bw2-vgiKwd-7FW2Z5-5DDWHc-weSgU-vXC8X-4v6Yx-fsnBrM-ufcFNb-mj9CNQ-aKucgK-rm1JK-p3JemQ-2fzKJV-oMxF3-faD6mK-fa1XNk-8VRU3W-nZpewH-oc9NCr-oMy3p-6NGW3e-6kANKN-oA4X5T-8VRTZS-bBdXxC-9eY26m-eTYiPm-3QvMNX-2CG8L-mhynyq-m7W9er-nxVPna-jwuMQJ-9DxTBv-zSiAb-7oP9iD
  https://www.flickr.com/search/?license=4%2C5%2C6%2C9%2C10&orientation=landscape&dimension_search_mode=min&height=640&width=640&advanced=1&media=photos&tags=zen%20garden
  https://en.wikipedia.org/wiki/Unix_philosophy
  http://homepage.cs.uri.edu/~thenry/resources/unix_art/ch01s06.html

  1. Welcome
  1. Benefits (what's in it for me?)
  1. Overview (what's on offer)
  1. History/Philosophy

  It's time to code cast!

  ## Why UNIX?

  [pitch benefits]

  * thousands of open source apps
  * speed (find files)
  * automation
  * power/control

  see: prag prog shell games

  * speed
  * not possible in UI
  * automatable
  * repeatable history

  ## A (very brief) history

  https://upload.wikimedia.org/wikipedia/commons/8/8f/Ken_Thompson_%28sitting%29_and_Dennis_Ritchie_at_PDP-11_%282876612463%29.jpg

  UNIX development began at Bell Labs in 1969 by Ken Thompson and, later, Dennis Ritchie, Joe Ossanna, and Rudd Canaday. The original development was on a PDP-7 computer; in 1971, it moved to the PDP-11.

  https://www.flickr.com/photos/mhx/4779975756/in/photolist-4nzZxV-7H7Dp9-7yYuoL-bnxQmn-bnxQon-9cGREk-bnxQzK-bnxQqF-9cGX6p-bnxQup-9cL3TU-7H7DUf-7H4CB5-9cL3qb-bnxQwK-6krQZg-88Vw46-5w3FQA-9cL2J3-6krNNe-6kvQKJ-8hoCg7-6krPSp-9KKpkX-6krUBn-6kw4cL-6kw38J-6krMGk-6krLA2-6krKCF-6krHv6-9KNdbE-9siddJ-3Lo4ud

  https://upload.wikimedia.org/wikipedia/commons/7/77/Unix_history-simple.svg

  * Dennis Richie
  * Linus
  * Stallman
  * Berkeley

  ## Unix philosophy

## Getting started

  1. Getting help

  https://www.flickr.com/photos/frosch50/12104437315/in/photolist-jrCpv6-53tWgz-82724T-53tWxx-53tWjP-53tWo6-5xfoPQ-53yavA-8fyho4-8fBx8b-5Moqaa-3xzBLw-5ZUiNm-bHMb2g-k9x4kj-4TqK1-4jhJLY-4ZXqfn-7ggS3o-6DZ1Lm-5kEHwW-6DZ1nU-2VV6Xn-4jhKdL-2v775V-7Ud6C9-MuzG8-5H7Q2j-5YrwUn-v5kS6c-9yNPPr-4xq3SZ-4xkuzy-4jdFFk-Bfem8-8fyhmi-8fyhk6-8fyhjk-rJSNvm-8En8Eo-8EiYGa-2pEg4P-3Au62u-3ApG9v-sbF7Vh-4jdFtP-kH8v1-7gtuP-dKPUcT-4xgiwn
  https://www.flickr.com/photos/tabsinthe/8286250862/

  $ apropos
  $ man
  $ man -- help

  type—Indicate how a command name is interpreted.
  which—Display which executable program will be executed.
  apropos—Display a list of appropriate commands.
  info—Display a command’s info entry.
  whatis—Display a very brief description of a command.

  1. History

  1. Keyboard shortcuts

## Shell environment

  https://www.flickr.com/search/?license=4%2C5%2C6%2C9%2C10&orientation=landscape&dimension_search_mode=min&height=640&width=640&advanced=1&tags=Environment
  https://www.flickr.com/photos/fr4dd/8425434209

  ~/.bashrc
  ~/.bash_login

  ## Prompt

  PS1=

  Codes/Color reference [add table to readme]

  ## History

  https://www.flickr.com/photos/82955120@N05/11108752186/in/photolist-hVDg17-gWQkHa-dX4smz-dPdnbP-dxYJM4-4nSSF4-dstJo4-doNnVF-dkbbGy-dgCrmM-dfQGjD-dcrHum-cYZC9u-cUFpoS-cUBdiu-bg6XKc-aNK69P-9TNefZ-9PATGj-9BQuMp-9A98u9-9x4Lwg-9w6aB8-8SEu6u-8Ag3qN-8tvhia-8pnyFR-8gwwbK-83YtHS-83G9vX-7PH6S6-7vsbJp-6khDPt-4nZsoH-4nZopn-4nZnVz-4nWCee-4nWh7c-4nXa4h-4nT674-4nX8PG-4nX8E1-4nWXx3-4nSSHx-4nWQ1A-4nWPAy-4nSELg-4nWJcG-4nSEnP-4nWJ1y

  HIST_SIZE

  ## Keyboard short cuts

  https://www.flickr.com/search/?license=4%2C5%2C6%2C9%2C10&orientation=landscape&dimension_search_mode=min&height=640&width=640&advanced=1&tags=keyboard&media=photos
  https://www.flickr.com/photos/nez/1371111259/in/photolist-36aiBi-6j76d5-4CG9Kz-4w9Uum-fcFao-9w84j8-7PLhcM-5EgjDt-5D1MRE-5sanqE-5fHutv-59165z-9bjAo7-6dt2kX-DVRPu-bd88Ue-6agycp-4SAVZF-4vigyt-4qi7s3-4q9VJ4-oExyaj-569niC-8uMcv9-L4qEw-9REK42-7MYZnV-4XuSdV-9REL1T-5GioZt-4oCwx1-i332at-bd86cF-8PuJUU-7xT3vr-7vMX3y-6axzXJ-4uopFH-3qTLZW-y9sqX-tFuRZ-tFuLc-6qjo7F-4yzNwB-MLHsd-prnBg-dcSNkC-5VWaLA-bd89Se-bd89ic

  $ CTL+r
  $ CTL+z
  $ CTL+d
  $ CTL+l

  ## Aliases

  ## Functions


# files
  https://www.flickr.com/photos/apothecary/5886670151/in/photolist-raJ5A6-dCecGb-qZXZUD-69Nzkm-qovZMz-q4b7zr-6gGrBF-spsSVA-6DASU6-pd3Qgt-9YbHWX-8uWBzH-9qWy6T-8kFone-816He9-813yjr-tMq5M4-urNQCK-fJZFLp-813yg2-813ypn
  http://c2.staticflickr.com/6/5303/5886670151_109fa7e33f_b.jpg

  https://www.flickr.com/photos/manc/1427691715/in/photolist-fBvhjC-6Mp5t-rcxXjH-aZWgk-nbk5Jt-3bai1p-6N6eHG-5Jp3Z-iM6SAr-5JC4WJ-2iYPPt-haFiqp-ff1Q69-eaQywa-7Q9dx4-66jsX3-cxMNgf-om93kf-iVavEz-jR1hx6-ovNdnb-ovMTUw-jbPGJT-xmEpJw-ovMQHF-feKnnc-haDVrh-ovMQPT-8KLE1A-8KHAe2-64Eu4i-jsPeY3-haDWkS-oNfUqy-bPGMNt-7xwX7e-i6yvNb-feKjyi-ngaxKh-j9QMxb-feKgPv-cdZrx7-haDY6M-dy6iDX-haE8hd-jBqec-4bRXQN-63cymo-vQ4EE-bPGL7R
  https://www.flickr.com/photos/evelynishere/3523642691/in/photolist-97eAVc-a6ND3Y-6nnAdc-6ctPVh-5ZvzFf-2G2Hhw-ffhBsf-rLPKsV-6fAXze-DU5m3-oiDv62-oiDfUN-feqC63-d7ckrL-oiDsP8-9HDbYF-7vQLCw-xaP8s2-xaF8q5-nXfffm-gurjJk-a6jj9w-a6gsSi-6pp53b-6pp4vY-6pp3VE-6pp3qj-9Bf2sP-7pUiPg-5A7sKt-yqSvN-5ovyY7-4GPZ8x-4GPYGV-4GU9PS-3ebcbT-3ebc7c-3ebc3t-3ebbYM-3ebbUH-3efznq-3ebbKc-3efxRQ-3ebapB-3ebaip-3efxBd-3eb9Pg-3efxfL-3efx97-3efxcJ
  https://www.flickr.com/photos/meanderingwa/8363274316/
  https://www.flickr.com/photos/andrewasmith/6157407129/

  ## Displaying

  $ ls
  $ less
  $ du
  $ wc
  $ head
  $ tail
  $ open
  $ nano/vim/emacs

  ## Modifying

  cp/mv, mkdir, rm

  Batch rename; see nubyonrails, learning Unix for OSX
  $ cp *-dt-* *-nt-* ~
  $ cp foo.{txt,md}

  $ mv
  $ mv foo.{txt,md}
  $ cp
  $ touch

  $ chown (permissions)
  $ chmod

  (Links)
  $ ln
  $ ln -s

  $ tar / gzip

  ## Displaying directories

  $ man hier (file system layout)
  $ tree
  $ df
  /Volumes see: OSX page

  ## Searching

  * Globbing/regex
  * find
  * locate
  * mdfind

# text
  1. explain pipes
  1. explain grep / ack (Basic regex)
  1. ack examples

  https://www.flickr.com/photos/rvoegtli/5327409891/in/photolist-97LnmF-dWahqB-nriDg4-5ZKant-aEYZL4-6tcMBE-5ZKa8D-fWDf6G-a7X6M9-vFBw1X-fWEdYX-fWDPM8-fWDWf9-fWDUxS-pntFC3-5cdVh3-4aoTCM-3ZWDpo-fWDicw-4DS7Wu-d2Kgx-97Ptd3-uQtbV9-4HMdPq-8sbEPw-m9nc8W-rGamHV-nZ91qC-dVbD5u-8MjoY1-7SxoJ2-6P4cuX-6gQmFD-dVbCV7-97LmEK-9HM8ip-d2KyB-rYxshx-5YsRX8-dV64Hn-dVbDGj-dV64eP-2gHaZf-2gCHGD-aAuboc-9rfzZj-7hqwXf-6nUV2p-7LqVz7-724NmM
  https://www.flickr.com/photos/afoncubierta/3224775921/in/photolist-5UXPwR
  https://www.flickr.com/photos/epsos/3777343342/in/photolist-6KMSzm-5PcjfU-nPBB3p-9cC6iW-nDiWyM-7pvQ27-5B27oJ-5mfbaD-cNdyo-afQ9p-awdir-4jwgUS-dPMJs-nUTK2r-k5JfXQ-bb96WM-9tL5J-fEvSSF-4Xad5v-wERCFT-q8MMa8-7wWzCF-8zowvU-79UvUf-9tL8n-nMV5KL-8HBjhC-bqMMo4-8K5Q7F-dahnk-9UBooU-9TwEn5-9CfAMG-5hmjgA-bENrpL-8L5ZDt-3d4M3i-c8t8x-i4DMQq-mZthaH-89EGWC-569m9L-2ovtso-fhirno-9TwENW-5hgY6T-tiKWp-dKGZTe-8TASxQ-vYcpbv

  see: DAS 019

  ## Redirection

  STDOUT/STDIN/STDERR

  ## Pipes

  $ cmp
  $ diff
  $ cut
  $ sort
  $ uniq
  $ while
  $ xargs

  advanced piping examples:

  * (Doug McIlroy)

  editors: nano/vi/emacs/jedit open

## Processes

  https://www.flickr.com/photos/onepointfour/13437748603
  https://www.flickr.com/photos/87895263@N06/8621155792/in/photolist-e8PFg7-qUgJ5N-h1KJp8-e8HW2P-g4fVt1-pMq8FA-gHX1pz-s9YcR4-7b6Bxv-ddThpa-njFxUE-doN3Ri-bMHJY2-e8J3SM-pJkzSk-qfYU62-pACFxk-8XKwu4-5svV7B-zkXog-5AeUUk-5i55Ka-pspRMA-dc3EWC-qkPLBB-oQu1VR-puQtWG-8TM4Cx-9VE68R-599hc3-c6gKq7-qRaiFD-5YFHH4-e8J39k-ncad5C-kRQWfK-k59rx-9DxNcq-hrBQpH-qxoMZP-4hsTha-qxk8od-pApfgA-9YaYLy-5K7Ny9-neYp1X-8zL2VW-55igSj-ppfdyk-54NUDu

  1. ps / pstree
  1. kill / killall
  1. nohup
  1. job control: bg, fg
  1. cron
  1. Deamons
  1. init
  1. launchctl
  1. top / htop
  1. at
  1. cron
  1. launchd

  (Job control see: DAS 008)

  https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html#//apple_ref/doc/uid/10000172i-CH1-SW2

## Networking

  https://www.flickr.com/photos/wwworks/2712985992/in/photolist-58JLko-58JLdy-58JL9G-8UFMJ2-mehDfW
  https://upload.wikimedia.org/wikipedia/commons/1/13/Nile_River_Delta_at_Night.JPG
  https://www.flickr.com/photos/jenny-pics/3734424634/in/photolist-6FZUkC-ah3rDf-6rk2Qf-zWeRv-npbuJZ-6rNawe-FMVAH-o4ZHuD-dmjp3S-9uqKG6-7eDyv4-jFEN1u-dmjkSk-puieT1-82bfbU-82bfbm-63nmeT-63narx-nbAtrV-d9K1Bc-7eDxQM-nmDAHq-atqHtw-5wdmiK-6W7Ee5-atqFUJ-8swLUs-8XguaX-4Pg5A-nVDQVe-kFddtH-cdjjsL-6U5Rze-9zNCwE-atqFmh-4qES4u-9vL3yN-4ZkBts-4HAWhb-9qYzYD-fkBDRw-apKj5o-8sD9kL-5X9uMJ-9fiFdu-4qAVj2-aqvvDW-Fr6Js-9tLDQ5-9vL8Zf
  https://www.flickr.com/photos/pagedooley/3143417443/
  https://www.flickr.com/photos/45818813@N05/4897407040/in/photolist-e963v1-58JLko-e8ZoNa-8sLuuq-58JLdy-58JL9G-e6HKgU-8UFMJ2-e6i5nT-e79ZyR-e7fF2o-mehDfW-e6i4XM-4C2AS3-e6i53t-e79ZFP-e7fDXQ-e7a1aV-95STgE-e7QStq-e963GG-e7fE53-e7fEhQ-e6i5Ex-e963Vj-e8Zp1r-e7a2hR-e8ZoWH-4BXmqF-e8ZoUi-e6i5tP-e6oHts-e6i4Sr-e5CMfM-e5CM2B-e624YK-e624RM-e8Zoyt-e6HKoQ-4BXiZr-e7fDG1-4C2AZW-e5CMGM-8zL677-aNGqCk-aNGd8v-aNG8zr-aNG6Qg-4C2vf7-e7a21M

  1. ssh/scp
  1. SSH config
  1. ftp
  1. curl
  1. lsof
  1. ifconfig

## Package management

  https://www.flickr.com/search/?license=4%2C5%2C6%2C9%2C10&orientation=landscape&dimension_search_mode=min&height=640&width=640&advanced=1&media=photos&tags=package
  https://www.flickr.com/photos/skohlmann/16238657422/in/photolist-qJXn77-rHS3W1-qQCY8T-v9rYRY-aDi321-4A15jm-kTR5RH-rMjckm-qZcDjY-8qQ7ng-pA4syi-s9jT1s-99ZHce-6qyvzc-7XM9sZ-wLKEpU-66o9iB-7mwoX8-5u8Nod-8N4AVD-cpNVy9-d3Vu5j-chf6Nj-rgJkH8-7K5fcz-asBCoE-bDGi5e-8N7GH9-rRSRgj-rW5nAW-7sbQz2-gxzpGa-cVcqew-8Ux54E-6zZF9N-4zVN6P-aUdHM2-a5ryhw-bVVjop-YeMgN-qiRFRg-oNMFd8-6MAMum-bD6GTJ-9dRGVj-xdPqsY-dkjepU-e5dxui-cpNVj1-br46u7
  https://www.flickr.com/photos/nsalt/2829985075/in/photolist-5j5pY8-6AE8Zt-4wjcDb-6vuDmF-g51x4e-asoxaf-mFYxCY-etgpMr-6rFZTz-ahwGjA-9bXNwL-bEtA2R-etgjE8-gvtDEX-rQ6dEG-etjCo5-egSbzN-dy2LPM-dw9BXS-dcA9k4-7egHcT-dvNfwB-etjJVL-8cEz2L-gvubH6-7A8LvM-ayeXeb-nrsg1Q-etjFaW-g24EY2-62K4Qb-qxog7-nrsd7V-etgsv2-dcBihW-qrWP3Q-etgzdX-4fmB8N-nyQsjq-etgoq8-fpB8Js-qhrxdr-penpDX-7AcwLQ-gvsNNs-fEsXTP-c871Xy-eNBSjb-dcxSAN-v7EGFy

  1. install home brew
  1. find app
  1. install app
  1. boot config
  1. taps/custom
  1. xcode-select -p
  1. xcode-select --install
  1. ruby/prog lang env
  1. remove app

  (reference ports/apt/rpm)
  see: TLCL pp150/183
  ? Install elastic search / mysql

  https://www.flickr.com/photos/gastev/2174504149
  https://www.flickr.com/photos/85264217@N04/9309444408/

  1. env bang
  1. loops
  1. conditionals
  1. ruby/python lang as shell script

## Outro

  https://www.flickr.com/photos/ivva/2062335626/in/photolist-49f1wN-e6i4XM-e7fDXQ-e7a1aV-e7fE53-e7fEhQ-6aYQA1-e6i5Ex-e8Zp1r-7DZMw9-9oE3Fo-e8ZoWH-e8ZoUi-e5CMfM-e5CM2B-e8Zoyt-4iRFgU-peAY8r-e6HKoQ-4BXiZr-7YXtjd-4C2AZW-aNGqCk-aNGd8v-aNG8zr-aNG6Qg-4C2vf7-e7a21M-e7a25V-4fdWoZ-9twnvu-5M2j6a-4BXmUT-e88bXF-e6C5Yv-e7KbAa-e7fDcq-Hzi8t-e963Vj-EWF7r-e7a2hR-4BXmqF-e6i5tP-e6oHts-e6i4Sr-e624YK-e624RM-28YTKB-e7fDG1-9BJXFC

  Recap

  ## Further reading
  
  * http://docstore.mik.ua/orelly/unix/upt
  * https://developer.apple.com/library/mac/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html#//apple_ref/doc/uid/TP40010672-CH2-SW7
  * http://www.mitchchn.me/2014/os-x-terminal/
  * Credits / attributions
  * Contact info (email address)
  * email list CTA
