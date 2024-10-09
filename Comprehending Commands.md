## Section 1: cat: not the pet,but the command
`hacker@commands~cat-not-the-pet-but-the-command:~$ cd /`
<br/>
`hacker@commands~cat-not-the-pet-but-the-command:/$ cat flag`
<br/>
Cat is a command used for reading out files. It multiplies files if multiple arguments are provided to it. I cded into the directory then read out the flag file using the cat command.
## Section 2: Catting absolute paths
`hacker@commands~catting-absolute-paths:~$ cat /flag`
<br/>
Reading out the flag file using an absolute path.
## Section 3: More catting practice
`hacker@commands~more-catting-practice:~$ cat /usr/share/xml-core/flag`
<br/>
Reading out the file without cding into the directory. The flag was hidden in a different directory. It was in the file /usr/share/xml-core/flag.
## Section 4: Grepping for a needle in a haystack
`hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt`
<br/>
The grep command has a function of searching  the file for lines of text containing the string to searched and print them to the console. The string to be searched in this case is 'pwn.college' and the path is /challenge/data.txt.
## Section 5:Listing Files
`hacker@commands~listing-files:~$ cd /challenge`
<br/>
`hacker@commands~listing-files:~$ ls`
<br/>
11126-renamed-run-2832  DESCRIPTION.md
<br/>
`hacker@commands~listing-files:/challenge$ cat 11126-renamed-run-2832`
<br/>
The ls command is used to list the files in a particular directory provided as argument and in the current directory if no argument is mentioned. I listed all the files in the /challenge directory to find the renamed file.
## Section 6: Touching Files
`hacker@commands~touching-files:~$ touch /tmp/pwn`
<br/>
`hacker@commands~touching-files:~$ touch /tmp/college`
<br/>
`hacker@commands~touching-files:~$ /challenge/run`
<br/>
Touch command is used to create files. I created 2 files using touch command and then excecuted /challenge/run.
## Section 7: Removing Files
`hacker@commands~removing-files:~$ rm delete_me`
<br/>
`hacker@commands~removing-files:~$ /challenge/check`
<br/>
rm command is used to remove or delete a particular file with the name of the file as an argument.
## Section 8:Hidden Files
`hacker@commands~hidden-files:~$ cd /`
<br/>
`hacker@commands~hidden-files:/$ ls -a`
<br/>
.   .dockerenv             bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-184513219630823  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
<br/>
`hacker@commands~hidden-files:/$ cat .flag-184513219630823`
<br/>
ls command doesnt list the files which start with a '.'. Thus to list out all the files a command 'ls -a' is used to list files beginning with '.' as well.
In the / directory I listed out all the files.
## Section 9:An epic filesystem Quest
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.   .dockerenv  bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
..  HINT        boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~an-epic-filesystem-quest:/$ cat HINT
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/networkx/algorithms/tests/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/local/lib/python3.8/dist-packages/networkx/algorithms/tests/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/networkx/algorithms/tests/__pycache__$ ls -a
.                                      test_distance_regular.cpython-38.pyc         test_planarity.cpython-38.pyc
..                                     test_dominance.cpython-38.pyc                test_polynomials.cpython-38.pyc
SECRET                                 test_dominating.cpython-38.pyc               test_reciprocity.cpython-38.pyc
__init__.cpython-38.pyc                test_efficiency.cpython-38.pyc               test_regular.cpython-38.pyc
test_asteroidal.cpython-38.pyc         test_euler.cpython-38.pyc                    test_richclub.cpython-38.pyc
test_boundary.cpython-38.pyc           test_graph_hashing.cpython-38.pyc            test_similarity.cpython-38.pyc
test_bridges.cpython-38.pyc            test_graphical.cpython-38.pyc                test_simple_paths.cpython-38.pyc
test_chains.cpython-38.pyc             test_hierarchy.cpython-38.pyc                test_smallworld.cpython-38.pyc
test_chordal.cpython-38.pyc            test_hybrid.cpython-38.pyc                   test_smetric.cpython-38.pyc
test_clique.cpython-38.pyc             test_isolate.cpython-38.pyc                  test_sparsifiers.cpython-38.pyc
test_cluster.cpython-38.pyc            test_link_prediction.cpython-38.pyc          test_structuralholes.cpython-38.pyc
test_communicability.cpython-38.pyc    test_lowest_common_ancestors.cpython-38.pyc  test_summarization.cpython-38.pyc
test_core.cpython-38.pyc               test_matching.cpython-38.pyc                 test_swap.cpython-38.pyc
test_covering.cpython-38.pyc           test_max_weight_clique.cpython-38.pyc        test_threshold.cpython-38.pyc
test_cuts.cpython-38.pyc               test_mis.cpython-38.pyc                      test_tournament.cpython-38.pyc
test_cycles.cpython-38.pyc             test_moral.cpython-38.pyc                    test_triads.cpython-38.pyc
test_d_separation.cpython-38.pyc       test_node_classification.cpython-38.pyc      test_vitality.cpython-38.pyc
test_dag.cpython-38.pyc                test_non_randomness.cpython-38.pyc           test_voronoi.cpython-38.pyc
test_distance_measures.cpython-38.pyc  test_planar_drawing.cpython-38.pyc           test_wiener.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/networkx/algorithms/tests/__pycache__$cc
at SECRET
Great sleuthing!
The next clue is in: /usr/share/X11/xkb/symbols

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/networkx/algorithms/tests/__pycache__$ccd /usr/share/X11/xkb/symbols
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/xkb/symbols$ ls -a
.       br            dk            gn          jp      lv              nl          sgi_vndr    trans
..      brai          dz            gr          jv      ma              no          sharp_vndr  tw
.BRIEF  bt            ee            group       ke      macintosh_vndr  nokia_vndr  shift       typo
af      bw            empty         hp_vndr     keypad  mao             np          si          tz
al      by            epo           hr          kg      md              olpc        sk          ua
altwin  ca            es            hu          kh      me              parens      sn          us
am      capslock      et            id          kpdl    mk              pc          sony_vndr   uz
apl     cd            eu            ie          kr      ml              ph          srvr_ctrl   vn
ara     ch            eurosign      il          kz      mm              pk          sun_vndr    xfree68_vndr
at      cm            fi            in          la      mn              pl          sy          za
au      cn            fo            inet        latam   mt              pt          terminate
az      compose       fr            iq          latin   mv              ro          tg
ba      ctrl          fujitsu_vndr  ir          level3  my              rs          th
bd      cz            gb            is          level5  nbsp            ru          tj
be      de            ge            it          lk      nec_vndr        rupeesign   tm
bg      digital_vndr  gh            jolla_vndr  lt      ng              se          tr
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/xkb/symbols$ cat .BRIEF
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/sympy/integrals/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/share/X11/xkb/symbols$ cd /usr/lib/python3/dist-packages/sympy/integrals/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/integrals/__pycache__$ ls -a
.                              intpoly.cpython-38.pyc          rde.cpython-38.pyc
..                             manualintegrate.cpython-38.pyc  risch.cpython-38.pyc
TRACE                          meijerint.cpython-38.pyc        singularityfunctions.cpython-38.pyc
__init__.cpython-38.pyc        meijerint_doc.cpython-38.pyc    transforms.cpython-38.pyc
deltafunctions.cpython-38.pyc  prde.cpython-38.pyc             trigonometry.cpython-38.pyc
heurisch.cpython-38.pyc        quadrature.cpython-38.pyc
integrals.cpython-38.pyc       rationaltools.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/integrals/__pycache__$ cat TRACE
Congratulations, you found the clue!
The next clue is in: /opt/linux/linux-5.4/include/config/no

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sympy/integrals/__pycache__$ cd /opt/linux/linux-5.4/include/config/no
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/no$ ls -a
.  ..  .NOTE  hz  hz.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/no$ cat .NOTE
Tubular find!
The next clue is in: /usr/lib/emacsen-common/packages

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/no$ ls /usr/lib/emacsen-common/packages
POINTER-TRAPPED  compat  install  remove
##Section 10:Making directories
`hacker@commands~making-directories:~$ mkdir /tmp/pwn`
<br/>
`hacker@commands~making-directories:~$ cd /tmp/pwn`
<br/>
`hacker@commands~making-directories:/tmp/pwn$ touch college`
<br/>
`hacker@commands~making-directories:/tmp/pwn$ /challenge/run`
<br/>
mkdir command is used to make a directory 
## Section 11:Finding Files
`hacker@commands~finding-files:~$ find / -name flag`
<br/>
Listed a list of files:
/home/hacker/flag
find: ‘/tmp/tmp.MiOQGWw5Zc’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/local/share/radare2/5.9.5/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/linux/linux-5.4/arch/ia64/hp/common/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
<br/>
After looking into each one of them:
<br/>
`hacker@commands~finding-files:~$ cat /opt/linux/linux-5.4/arch/ia64/hp/common/flag`
<br/>
File command is used to search for the file taking arguments of location or serach criteria. If nothing is provided it looks through all the files.
## Section 12: Linking Files


