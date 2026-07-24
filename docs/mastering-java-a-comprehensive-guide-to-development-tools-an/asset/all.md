Mastering java

A comprehensive guide to development tools and techniques

Lena neill

**© copyright 2023 by ryan roffe - all rights reserved.**

The text is a copyright disclaimer for a book authored by ryan roffe, stating that the reproduced content aims to provide accurate information. However, readers are cautioned that the author and publisher are not experts on the topics discussed, and any suggestions are for entertainment purposes only.

Professionals should be consulted before acting on any recommendations. The disclaimer is considered legally binding by relevant associations, and unauthorized reproduction is prohibited. The information is presented as truthful, and the reader assumes responsibility for its use.

The content is intended for informational purposes, and trademark mentions do not imply endorsement

Table of contents

[Introduction](#index_split_003.html_id_Toc157095478)

[Chapter 1: java basics](#index_split_004.html_id_Toc157095479)

[Chapter 2 variables](#index_split_005.html_id_Toc157095480)

[Chapter 3: java basics](#index_split_006.html_id_Toc157095481)

[Chapter 4: java environment](#index_split_007.html_id_Toc157095482)

[Chapter 5: objects and classes](#index_split_008.html_id_Toc157095483)

[Chapter 6: proper working code examples](#index_split_009.html_id_Toc157095484)

[Chapter 8: decision making and loop control](#index_split_010.html_id_Toc157095485)

[Chapter 9: adt, data structure, and java collections](#index_split_011.html_id_Toc157095486)

[Chapter 10: file handling](#index_split_012.html_id_Toc157095487)

[Chapter 11: collections](#index_split_013.html_id_Toc157095488)

[Conclusion](#index_split_014.html_id_Toc157095489)

# Introduction

Java  is  a  wide,ly-use,d  programming  language,  on  the,  we,b  and  in  computing  applications.  it  is  a  fre,e,  download  solution  that  allows  use,rs  to  acce,ss  the,  late,st  ve,rsions  and  imple,me,nt  update,s.  this  particular  programming  language,  is  pre,se,nt  in  the,  majority  of  today’s  we,b  applications  and  computing  te,chnologie,s.  java’s  scalable,  characte,ristics  make,  it  suitable,  for  de,ployme,nt  in  a  wide,  range,  of  applications,  including  apps  for  small  e,le,ctronic  de,vice,s  like,  ce,ll  phone,s  and  software,  solutions  for  large,  scale,  ope,rations  such  as  data  ce,nte,rs.  the,  growing  pre,fe,re,nce,  for  de,ploying  java  is  attributable,  to  its  robust  functional  fe,ature,s  and  sound  se,curity  cre,de,ntials.

Java  is  a  programming  language,  that  is  built  by  sun  microsyste,ms,  which  was  late,r  take,n  ove,r  by  the,  oracle,  corporation.  it  is  de,signe,d  to  run  on  any  ope,rating  syste,m  that  supports  java.  this  is  what  made,  the,  language,  so  popular,  be,cause,  the,  de,ve,lope,r  just  had  to  write,  the,  program  once,,  and  the,  program  could  the,n  run  on  any  ope,rating  syste,m  without  the,  ne,e,d  for  the,  programme,r  to  change,  the,  code,.

Most  of  the,  mode,rn  applications  built  around  the,  world  are,  made,  from  the,  java  programming  language,.  most  of  the,  se,rve,r-side,  and  busine,ss  logic  compone,nts  of  major  applications  are,  built  on  the,  java  programming  language,.

During  the,  e,ntire,  course,  of  this  book,  you  will  le,arn  how  to  write,  programs  such  as  the,  one,  above,,  and  also  le,arn  advance,d  conce,pts  that  will  e,nable,  you  to  start  writing  comple,te,  application  programs.

Some,  of  the,  de,sign  goals  for  java  are,  me,ntione,d  be,low:

Zthe,  language,  is  inte,nde,d  to  be,  writte,n  once,  and  have,  the,  ability  to  be,  run  on  any  ope,rating  syste,m.

the,  language,  should  provide,  support  for  nume,rous  software,  e,ngine,e,ring  principle,s.  portability  is  an  important  factor.  this  is  why  java  has  the,  ability  to  run  on  windows,  linux,  and  the,  macos  ope,rating  syste,m.

Support  for  inte,rnationalization  is  ve,ry  important.

Java  is  inte,nde,d  to  be,  suitable,  for  writing  applications  for  both  hoste,d  and  e,mbe,dde,d  syste,ms.

Othe,r  de,sign  goals  are,  discusse,d  ne,xt:

### Strong  type,  che,cking

Java  is  a  strong  type,  language,.  e,ve,ry  variable,  that  is  de,fine,d  ne,e,ds  to  be,  attache,d  to  a  data  type,.

You  don’t  ne,e,d  to  unde,rstand  the,  comple,te,  program  for  now,  but  le,t’s  just  have,  a  quick  look  at  2  line,s  of  the,  code,.

1)  int  i=5;

He,re,  we,  are,  de,fining  some,thing  known  as  a  variable,,  which  is  use,d  to  hold  a  value,.  the,  value,  that  can  be,  store,d  de,pe,nds  on  the,  data  type,.  in  this  e,xample,,  we,  are,  saying  that  ‘i’  is  of  the,  type,  ‘int’  or  inte,ge,r,  which  is  a  nume,ric  data  value,.

### Array  bounds  che,cking

At  runtime,,  java  will  che,ck  whe,the,r  the,  array  has  the,  re,quire,d  numbe,r  of  value,s  de,fine,d.  if  one,  trie,s  to  acce,ss  a  value,  which  is  outside,  the,  bounds  of  the,  array,  an  e,xce,ption  will  be,  thrown.

You  don’t  ne,e,d  to  unde,rstand  the,  comple,te,  program  for  now,  but  le,t’s  just  have,  a  quick  look  at  the,  following  line,s  of  the,  code,.

1.  Int[]  array1  =  ne,w  int[2];

He,re,  we,  are,  de,claring  an  array,  which  is  a  se,t  of  inte,ge,r  value,s.  the,  value,  of  ‘2’  me,ans  that  we,  can  only  store,  two  value,s  in  the,  array.

2)  array1[0]  =  1;

Array1[1]  =  2;

Array1[2]  =  3;

With  this  code,,  we,  can  se,e,  that  we,  are,  assigning  3  value,s  to  the,  array.  whe,n  you  run  this  program,  you  will  ge,t  an  e,rror  be,cause,  the,  program  will  se,e,  that  the,  array  has  gone,  out  of  its  maximum  allowable,  bounds  of  two.  you  will  ge,t  the,  be,low  e,rror  at  runtime,.  e,xce,ption  in  thre,ad  "main"  java.lang.arrayinde,xoutofboundse,xce,ption:  2

At  he,lloworld.main(he,lloworld.java:8)

### Why  java  is  important?

Ne,xt,  java  has  syntax  and  fe,ature,s  that  re,se,mble,  othe,r  programming  language,s  like,  c  and  c++.  if  you  have,  any  prior  programming  e,xpe,rie,nce,,  you  will  find  le,arning  java  a  bre,e,ze,.  e,ve,n  if  you  are,  totally  ne,w  to  programming,  you  can  re,st  assure,d  that  java  is  de,signe,d  to  be,  a  re,lative,ly  e,asy  language,  to  le,arn.  most  programme,rs  find  it  e,asie,r  to  le,arn  java  than  say,  c  or  c++.

Java  is  also  de,signe,d  to  be,  platform-inde,pe,nde,nt.  as  me,ntione,d  e,arlie,r,  java  code,  is  compile,d  into  byte,code,  first,  which  can  be,  run  on  any  machine,  that  has  the,  java  virtual  machine,.

He,nce,  with  java,  you  can  write,  the,  code,  once,  and  run  it  anywhe,re,  you  want.

### Why  java?

Of  course,,  one,  of  the,  ke,y  re,asons  to  use,  java  is  its  focus  on  obje,ct-orie,nte,d  programming.

Obje,ct-orie,nte,d  programming,  or  “oop”  is  a  type,  of  programming  language,  mode,l  which  allows  the,  program’s  code,  to  be,  organize,d  around  data,  rathe,r  than  functions  and  logic,  which  is  known  as  proce,dural  programming.

The,se,  “data  cluste,rs”  are,  organize,d  into  things  calle,d  “obje,cts,”  he,nce,  the,  monike,r  of  “obje,ct-orie,nte,d  programming.”

The,se,  obje,cts  are,  cre,ate,d  by  some,thing  calle,d  “classe,s,”  unde,rstood  he,re,  in  the,  traditional  se,nse,  of  how  classe,s  are,:  type,s  of  obje,cts,  allowing  the,  programme,r  to  “classify”  the,m  according  to  two  major  crite,ria:  attribute,s  and  me,thods.

The,  attribute,s  of  a  class  are,  the,  raw  data  that  will  cre,ate,  the,  obje,ct:  the,se,  are,  its  de,scriptors,  such  as  the,  value,s  that  it  posse,sse,s,  and  othe,r  re,le,vant  data  that  will  make,  up  the,  obje,ct.  the,  se,cond  crite,rion  is  the,  “me,thod”  of  the,  obje,ct.

This  “me,thod”  is  the,  be,havior,  or  the,  logical  se,que,nce,s  containe,d  within  the,  class,  de,scribing  how  it  inte,racts  or  can  be,  inte,racte,d  with  native,ly.

# Chapte,r  1:  java  basics

Of  course,,  one,  of  the,  ke,y  re,asons  to  use,  java  is  its  focus  on  obje,ct-orie,nte,d  programming.  obje,ct-orie,nte,d  programming,  or  “oop”  is  a  type,  of  programming  language,  mode,l  which  allows  the,  program’s  code,  to  be,  organize,d  around  data,  rathe,r  than  functions  and  logic,  which  is  known  as  proce,dural  programming.

The,se,  obje,cts  are,  cre,ate,d  by  some,thing  calle,d  “classe,s,”  unde,rstood  he,re,  in  the,  traditional  se,nse,  of  how  classe,s  are,  type,s  of  obje,cts,  allowing  the,  programme,r  to  “classify”  the,m  according  to  two  major  crite,ria:  attribute,s  and  me,thods.

The,  attribute,s  of  a  class  are,  the,  raw  data  that  will  cre,ate,  the,  obje,ct:  the,se,  are,  its  de,scriptors,  such  as  the,  value,s  that  it  posse,sse,s,  and  othe,r  re,le,vant  data  that  will  make,  up  the,  obje,ct.

The,  se,cond  crite,rion  is  the,  “me,thod”  of  the,  obje,ct.

In  orde,r  to  make,  this  cle,are,r,  say  that  the,re,  is  a  class  “human.”  this  “class”  will  have,  attribute,s  such  as  he,ight,  we,ight,  ge,nde,r,  and  race,.  the,  “human”  class  can  also  have,  me,thods  such  as  “run,”  “walk,”  “talk.”  the,se,  the,ore,tical  compone,nts  make,  up  the,  “human”  class,  a  blue,print  for  an  obje,ct.

Now  that  the,  class  has  be,e,n  de,fine,d,  the,  programme,r,  if  the,y  so  wish,  can  cre,ate,  an  obje,ct  using  the,  “human”  class  as  a  blue,print.

The,y  can  invoke,  the,  class  “human”  and  “populate,”  its  attribute,s,  giving  it  a  spe,cific  he,ight,  we,ight,  ge,nde,r,  and  race,.  in  addition,  the,  obje,ct  alre,ady  has  built-in  functions  such  as  “run,”  “walk,”  and  “talk,”  so  upon  the,  cre,ation  of  an  obje,ct,  le,t’s  say  name,d  “mike,”  from  the,  “human”  class,  it  alre,ady  contains  the,  functions  to  run,  walk,  and  talk,  without  ne,e,d  for  the,  programme,r  to  code,  those,  spe,cific  functions  again,  as  the,y  are,  alre,ady  “inhe,re,nt”  in  the,  cre,ate,d  obje,ct.

In  a  nutshe,ll,  that  is  what  obje,ct-orie,nte,d  programming  is  me,ant  to  be,:  a  way  of  programming  that  allows  the,  programme,r  to  draw  on  pre,-de,fine,d  classe,s  so  that  it  will  be,  e,asie,r  to  de,scribe,  the,m  and  use,  the,ir  inte,rnal,  or  built-in  functions  in  orde,r  to  ope,rate,  the,m.

Assuming  that  the,  re,ade,r  is  not  a  total  ne,wbie,  to  programming,  and  has  be,e,n  introduce,d  to  the,  world  of  programming  using  c  or  anothe,r  proce,dural––he,avy  language,,  the,  ne,xt  logical  que,stion  would  be,:  why  e,ve,n  use,  obje,ct-orie,nte,d  programming?

We,ll,  one,  of  its  main  advantage,s  is  that  in  the,  long  run,  it  save,s  time,.

Proce,dural  programming  is  usually  much  quicke,r  and  more,  straightforward  in  simple,r  algorithms  and  programs;  rathe,r  than  having  to  construct  and  de,fine,  a  class,  and  cre,ate,  an  obje,ct  base,d  on  that  class,  all  the,  programme,r  re,ally  has  to  do  is  to  simply  de,clare,  the,  ne,ce,ssary  variable,s  and  write,  the,  functions,  and  cre,ate,  the,  algorithm  in  orde,r  to  solve,  the,  proble,m  that  the,y  ne,e,d  the,  code,  to  addre,ss.

Howe,ve,r,  whe,n  it  come,s  to  more,  comple,x  programs,  ne,e,ding  more,  comple,x  solutions,  this  is  whe,re,  obje,ct-orie,nte,d  programming  be,gins  to  shine,,  and  this  is  whe,re,  it  starts  to  show  its  stre,ngth.

In  a  lot  of  programs,  the,re,  will  be,  time,s  that  the,re,  will  be,  a  numbe,r  of  “obje,cts”  or  data  cluste,rs  that  have,  to  be,  groupe,d  toge,the,r,  and  that  the,  programme,r  will  be,  tre,ate,d  in  a  ce,rtain  way.

This  is  what  “classe,s”  are,  me,ant  to  addre,ss.

Inste,ad  of  de,claring  a  ne,w  se,t  of  variable,s  pe,r  data  cluste,r,  the,y  can  simply  draw  on  a  pre,-made,  “class”  and  cre,ate,  a  ne,w  “obje,ct.”

Le,t’s  se,e,  how  this  would  work  in  practice,.

If  a  programme,r  we,re,  to  code,  a  che,ss  game,  in  proce,dural  fashion,  the,n  the,y  would  have,  to  manually  de,scribe,  e,ach  and  e,ve,ry  pie,ce,,  all  sixte,e,n  pawns,  four  bishops  and  four  knights,  four  rooks,  two  que,e,ns,  and  two  kings.  in  addition,  the,y  will  have,  to  write,  the,  functions  that  allow  e,ach  pie,ce,  to  move,  in  its  own  se,parate,  way.

Howe,ve,r,  if  the,  programme,r  make,s  use,  of  obje,ct-orie,nte,d  programming,  inste,ad  of  having  to  code,  sixte,e,n  pawns,  four  bishops,  four  knights,  four  rooks,  two  que,e,ns,  two  kings,  the,y  simply  have,  to  code,  six  classe,s:  one,  class  to  de,scribe,  e,ach  pie,ce,  on  the,  board.

The,  programme,r  can  now  simply  include,  the,  move,me,nt  functions  within  e,ach  class,  and  have,  the,  attribute,s  de,scribe,  the,ir  position:  whe,the,r  the,y’re,  white,  king’s  pawn,  or  black  que,e,n’s  pawn,  the,se,  are,  all  things  that  can  be,  inse,rte,d  through  the,  “attribute,s”  portion  of  the,  “pawn”  class.  inste,ad  of  thirty––two  cluste,rs  of  code,,  the,  programme,r  only  has  to  do  six.

Now  it’s  much  e,asie,r,  much  shorte,r,  and  also  much  more,  e,le,gant.

### Java  toke,ns

Java  toke,ns  are,  the,  value,s  that  are,  smalle,r  than  othe,r  inte,ge,rs.

The,se,  numbe,rs  are,  going  to  fall  be,twe,e,n  the,  value,  of  -32768  and  32767.

The,  code,  that  i  have,  be,e,n  using  is  not  going  to  work  for  shorts,  inste,ad,  i  am  going  to  ne,e,d  to  use,  the,  short  function  so  that  i  can  make,  sure,  that  the,  value,s  are,  going  to  fall  be,twe,e,n  the,  se,t  limitations.

Large,  value,s  are,  going  to  be,  store,d  inside,  of  a  double,  value,  along  with  floating-point  value,s.

A  double,  doe,s  not  have,  to  be,  use,d  if  i  can  use,  a  floating-point.  as  i  am  storing  a  floating  variable,.

I  am  going  to  ne,e,d  to  put  a  le,tte,r  at  the,  e,nd  of  my  value,  amount.  this  value,  should  be,  f  be,cause,  it  is  a  floating-point  numbe,r.

### Ke,ywords

In  java,  the,  boole,an  type,  re,fe,rs  to  false,  or  true,  value,s.  j

Ava  finds  out  if  it  is  true,  or  false,  using  the,  re,se,rve,d  ke,ywords.  the,re,fore,,  a  boole,an  e,xpre,ssion  type,  will  assume,  one,  of  the,se,  value,s.

An  e,xample,  to  de,monstrate,  include,:

The,re,  are,  a  fe,w  things  to  note,  about  this  program.

First,  the,  println(),  displays  a  boole,an  value,.  se,condly,  the,  boole,an  value,s  control  the,  flow  of  an  if  state,me,nt.

You  don’t  ne,e,d  to  go  a  long  way  in  writing  the,  boole,an  type,  this  way:  if  (b

==  true,)

The,  re,sult  shown  by  the,  ope,rator,  such  as  <  is  boole,an.  it  is  one,  of  the,  re,asons  why  we,  have,  the,  e,xpre,ssion  11  >  8  showing  the,  value,  true,.

In  addition,  the,  othe,r  pair  of  pare,nthe,se,s  ne,ar  the,  11  >  8  is  important  since,  plus  come,s  be,fore,  the,  >.

### Ide,ntifie,rs

The,  top  laye,r  of  the,  diagram  above,  is  for  the,  ide,ntifie,r  or  name,.

This  top  laye,r  is  the,  name,  you  give,  to  a  class.  the,  name,  should  spe,cifically  ide,ntify  and  also  de,scribe,  the,  type,  of  obje,ct  as  se,e,n  or  e,xpe,rie,nce,d  by  the,  use,r.

In  simple,  te,rms,  the,  name,  or  ide,ntifie,r  should  ide,ntify  the,  class.

### Ope,rators

Java  has  an  e,xte,nsive,  list  of  ope,rator  e,nvironme,nt.

If  you  are,  wonde,ring  what  an  ope,rator  is,  you  can  look  at  it  as  a  symbol  that  conve,ys  a  spe,cific  me,ssage,  to  the,  compile,r  to  carry  out  a  logical  or  mathe,matical  ope,ration.  in  java,  you  will  inte,ract  with  four  classe,s  of  ope,rators.

The,  four  classe,s  include,:

![image](images/image100.png)![image](images/image100.png)![image](images/image100.png)![image](images/image100.png)logical  ope,rator  bitwise,  ope,rator  re,lational  ope,rator  arithme,tic  ope,rator

Like,  othe,r  compute,r  language,s,  java  has  a  de,fine,d  list  of  additional  ope,rators  to  take,  care,  of  ce,rtain  spe,cific  sce,narios.

Whe,n  it  come,s  to  le,arning  java  programming  language,,  or  any  programming  language,  for  that  matte,r,  the,re,  are,  five,  basic  conce,pts  you  must  unde,rstand  be,fore,  you  ge,t  starte,d.

![image](images/image100.png)the,se,  five,  basic  conce,pts  include,:  variable,s

![image](images/image100.png)![image](images/image100.png)![image](images/image100.png)data  structure,s  control  structure,s  syntax

![image](images/image100.png)tools

E,ach  of  the,se,  conce,pts  will  be,  thoroughly  e,xplaine,d  on  a  be,ginne,r’s  le,ve,l  to  e,nsure,  that  the,y  are,  unde,rstood.

### Se,parators

The,y  are,  not  suitable,  for  high-le,ve,l  abstraction:  note,  that  a  lot  of  the,se,  programs  make,  use,  of  low-le,ve,l  constructs  which  are,  primarily  use,d  for  low-le,ve,l  abstraction.

The,  usual  approach  with  the,se,  programming  language,s  is  that  the,y  focus  on  the,  machine,––how  to  make,  a  compute,r  do  some,thing  rathe,r  than  how  the,se,  functions  can  he,lp  solve,  the,  issue,s  of  a  use,r.

The,se,  language,s  de,al  with  the,  minute,  de,tails,  which  is  alre,ady  be,yond  the,  scope,  of  high-le,ve,l  abstraction,  which  is  the,  more,  common  approach  that  we,  se,e,  today.

In  low-le,ve,l  abstraction,  data  structure,s  and  algorithms  are,  take,n  se,parate,ly,  whe,re,as  the,se,  are,  take,n  as  a  whole,  in  high-le,ve,l  abstraction.

### Lite,rals

Whe,n  it  come,s  to  lite,rals  in  java,  we,  me,an  the,  fixe,d  value,s  which  appe,ar  in  the,  form  in  which  human  be,ings  can  re,ad.  we,  can  say  the,  numbe,r  200  is  lite,ral.  most  of  the,  time,,  lite,rals  can  be,  constants.

Lite,rals  are,  important  in  a  program.  in  fact,  most  java  programs  use,  lite,rals.  some,  of  the,  programs  we,  have,  alre,ady  discusse,d  in  this  book  use,  lite,rals.

Lite,rals  in  java  can  fall  on  various  primitive,  data  type,s.

The,  manne,r  in  which  e,ve,ry  lite,ral  is  shown  is  de,te,rmine,d  by  its  type,.  like,  it  was  me,ntione,d  some,  time,  back,  we,  e,nclose,  characte,r  constants  in  single,  quote,s  such  as  ‘c’  and  ‘%.’

We,  de,fine,  lite,rals  in  inte,ge,rs  without  involving  the,  fractional  part.  for  instance,,  12  and  -30  are,  inte,ge,r  lite,rals.  a  floating-point  lite,ral  should  contain  the,  de,cimal  point  plus  the,  fractional  part.  12.389  is  a  floating  lite,ral.

Java  furthe,r  pe,rmits  for  one,  to  apply  the,  scie,ntific  notation  for  the,  floating-  point  lite,rals.

Inte,ge,r  lite,rals  contain  int  value,,  and  anyone,  can  initialize,  the,m  with  a  variable,  of  short,  byte,,  and  char.

### Comme,nts

Whe,n  this  occurs,  we,  call  the,  gre,y’s  comme,nts.  in  the,  running  stage,s  of  the,  program,  the,  gre,y’s  (comme,nts)  are,  moot.

This  is  to  me,ans  that  you  can  use,  the,  comme,nt  fe,ature,  to  state,  or  e,xplain  what  the,  code,  you  are,  cre,ating  wants  to  achie,ve,.

You  can  achie,ve,  this  by  typing  two  slashe,s  and  the,n  the,  comme,nt.  he,re,  is  a  sample,.

//place,  your  single,  line,  comme,nt  he,re,

You  can  have,  more,  than  one,  comme,nt  line,  by  doing  e,ithe,r  of  the,  following:

//we,  are,  going  to

//spre,ad  the,  comme,nts  into  two  or

/*

This  comme,nt  spre,ads  ove,r  two  line,s

*/

If  you  look  at  the,  comme,nt  above,,  you  will  notice,  that  it  starts  with  /*  but  e,nds  with  */

Additionally,  if  you  look  at  the,  pre,vious  image,  (figure,  8,  you  will  notice,  that  the,re,  are,  comme,nts  that  be,gin  with  a  single,  forward  slash  and  two  aste,risks  (/**),  but  e,nd  with  one,  aste,risk  and  one,  forwards  slash;  this  is  calle,d  a  javadoc  comme,nt.

# Chapte,r  2  variable,s

### What  are,  variable,s?

A  variable,,  on  the,  othe,r  hand,  is  an  "obje,ct"  that  contains  a  spe,cific  data  type,  and  it's  assigne,d  or  re,ce,ive,d  value,.  it  is  calle,d  a  variable,  be,cause,  the,  value,  containe,d  can  change,  according  to  how  it  is  use,d  in  the,  code,,  how  the,  code,r  can  de,clare,  its  value,,  or  e,ve,n  how  the,  use,r  of  the,  program  choose,s  to  inte,ract  with  it.  a  variable,,  in  short,  is  a  storage,  unit  for  a  data  type,.  having  acce,ss  to  variable,s  allow  programme,rs  to  conve,nie,ntly  labe,l  and  call  store,d  value,s  at  hand.

### Type,s  of  variable,s  in  java

Java  re,quire,s  the,  programme,r  to  use,  de,claration  state,me,nts,  line,s  of  code,  use,d  to  de,clare,  variable,s  and  de,fine,  the,m  by  spe,cifying  the,  particular  data  type,  and  name,.  java  has  a  spe,cific  way  of  tre,ating  variable,s,  by  de,fining  variable,s  as  containe,rs  that  contain  a  ce,rtain  type,  and  value,  of  information,  unlike,  some,  language,s  such  as  python,  which  only  re,quire,s  a  de,claration  of  a  variable,,  and  the,  variable,  can  dynamically  change,  its  type,;  java  variable,s  are,  static,  which  re,tain  the,ir  type,  once,  de,clare,d.

Int  numbe,r  =  20;

Boole,an  comple,te,d  =  true,;  string  he,llo  =  “he,llo  world!”

The,  syntax  in  de,claring  is  se,e,n  in  the,  pre,vious  e,xample,s,  with  the,  type,  of

The,  variable,  coming  first,  the,n  the,  name,  of  the,  variable,,  the,n  the,  value,.  note,  as  we,ll  that  the,  de,claration  state,me,nt  can  be,  compose,d  of  multiple,  de,clarations  in  one,  line,,  as  in  the,  following  e,xample,:

Int  numbe,r  =  20,  boole,an  comple,te,d  =  true,,  string  he,llo  =  “he,llo  world!”;

Java  variable,s  can  be,  de,clare,d  without  any  value,  at  the,  start;  in  case,s  such  as  the,se,,  java  choose,s  to  de,clare,  the,se,  variable,s  with  a  particular  de,fault  value,,  for  e,xample,:

Byte,  a;

Short  num;

Boole,an  answe,r;

Will  re,sult  in  the,  value,s  0,  0,  and  false,,  re,spe,ctive,ly.  a  more,  comple,te,  list  of  de,fault  value,s  is  as  follows:  the,  byte,,  short,  int,  and  long  data  type,s  will  all  re,sult  in  a  de,fault  value,  of  0,  while,  the,  float  and  double,  data  type,s  will  have,  a  de,fault  0.0  value,,  the,  char  data  type,  will  re,sult  in  ‘u\0000’  value,,  a  string  or  any  othe,r  obje,ct  will  have,  a  null  de,fault  value,,  and  all  boole,ans  will  be,gin  with  a  false,  de,fault  value,.

In  java,  variable,s  are,  static  whe,n  de,clare,d,  me,aning  that  the,  programme,r  must  de,fine,  the,  data  type,  that  the,  variable,  will  be,  containing.  to  illustrate,,  if  we,  wish  to  use,  a  variable,  num  to  store,  a  numbe,r,  we,  would  first  have,  to  de,clare,  the,  variable,:  "int  num,"  be,fore,  we,  can  assign  a  value,,  such  as  "num

=  10."

The,  proce,ss  above,  is  usually  known  as  and  re,fe,rre,d  to  as  an  "assignme,nt  state,me,nt,"  whe,re,  a  value,  is  assigne,d  to  the,  variable,  as  de,clare,d  by  the,  programme,r.  howe,ve,r,  one,  promine,nt  thing  about  how  java,  and  in  fact  how  most  programming  language,s,  works  is  that  in  the,  assignme,nt  state,me,nt,  such  as  in  our  e,xample,  of  num  =  10,  the,  actual  value,  store,d  is  the,  one,  on  the,  right  side,  of  the,  e,quals  sign,  the,  value,  of  10,  and  num  is  just  the,  "marke,r"  to  call  that  store,d  value,.  this  is  why  the,re,  are,  many  java  programme,rs  that  te,nd  to  pre,fe,r  the,  jargon  of  "ge,tting"  a  value,  rathe,r  than  "assigning,"  though  for  the,  most  part,  the,y  may  be,  e,mploye,d  inte,rchange,ably,  and  outside,  of  some,  rare,  sce,nario,  function  mostly  the,  same,  way.

Note,,  howe,ve,r,  that  once,  value,s  have,  be,e,n  assigne,d  to  variable,s,  functions  ne,e,d  to  be,  carrie,d  out  in  orde,r  for  the,  data  inside,  that  variable,  to  change,  its  data  type,.

### Naming  a  variable,

Cre,ating  variable,s  is  an  e,asy  task,  e,spe,cially  give,n  how  java  programme,rs  te,nd  to  cre,ate,  and  name,  the,m  afte,r  the,  data  type,  or  the,  purpose,  of  what  the,  variable,  will  store,.  howe,ve,r,  the,re,  are,  a  fe,w  rule,s  whe,n  it  come,s  to  naming  the,se,  variable,s,  e,lse,  java  will  not  re,cognize,  it,  and  an  e,rror  me,ssage,  will  re,sult.  the,  main  re,strictions  around  variable,  name,s  are,  that  it  should  not  be,gin  with  a  spe,cial  characte,r,  such  as  an  unde,rscore,  or  a  numbe,r.  howe,ve,r,  variable,  name,s  can  consist  of  characte,rs  such  as  le,tte,rs  and  numbe,rs,  and  e,ve,n  an  unde,rscore,,  provide,d  that  the,  unde,rscore,  is  not  place,d  at  the,  start.

No  othe,r  characte,rs  may  be,  use,d,  such  as  the,  #  or  e,ve,n  z,  as  the,se,  spe,cial  characte,rs  have,  diffe,re,nt  use,s  in  java,  and  thus  will  not  be,  re,cognize,d  in  a  variable,  name,.

While,  those,  are,  the,  major  rule,s,  he,re,  are,  some,  tips  whe,n  it  come,s  to  naming  variable,s.  the,  variable,  name,  should  be,  de,scriptive,,  as  in  longe,r  code,s  it  may  be,  difficult  to  re,call  just  what  "x"  is  for.  having  a  variable,  name,  such  as  "count"  or  "output"  is  much  e,asie,r  to  re,call  as  compare,d  to  having  a  ge,ne,ric  "x"  or  "y"  and  will  he,lp  in  avoiding  confusion.  in  addition  to  be,ing  de,scriptive,,  variable,s  will  also  be,  e,asie,r  to  use,  if  the,ir  name,s  are,  ke,pt  fairly  short.  while,  having  a  variable,  name,  such  as  banking  information  account  re,cords  is  ve,ry  de,scriptive,,  typing  it  re,pe,ate,dly  as  ne,e,de,d  in  the,  program  will  ge,t  e,xhausting,  and  having  longe,r  variable,  name,s  incre,ase,  the,  chance,s  of  typographical  e,rrors,  which  will  le,ad  to  bugs  in  the,  code,,  re,sulting  in  a  run  -  time,  e,rror  or  the,  code,  not  working  as  inte,nde,d,  or  working,  but  introducing  bugs  along  the,  way.  note,  as  we,ll  that  it  has  always  be,e,n  a  practice,  for  java  variable,s  to  be,  writte,n  in  all  lowe,r––case,  le,tte,rs,  and  while,  the,re,  is  no  re,striction  on  capitalization,  ke,e,ping  things  in  lowe,rcase,  simplifie,s  things,  as  a  misse,d  capitalization  may  re,sult  in  the,  variable,  not  be,ing  re,cognize,d,  as  java  re,ads  an  uppe,r––case,  le,tte,r  as  an  e,ntire,ly  diffe,re,nt  characte,r  ve,rsus  a  lowe,r––case,  le,tte,r.

### Java  primitive,  type,s

Me,thod  naming  conve,ntions

We,  shall  re,visit  the,  naming  conve,ntions  in  java  since,  you  will  be,  using  me,mbe,r  me,thods.  me,thods  in  java  programming  pe,rform  ope,rations,  the,y  also  re,ce,ive,  any  argume,nt  provide,d  by  a  calle,r,  and  it  can  also  re,turn  a  re,sult  of  an  ope,ration  to  a  calle,r.  he,re,’s  the,  syntax  for  de,claring  a  me,thod:

[acce,ss  control  modifie,r]  re,turn  type,  me,thodname,  ([se,t  of  parame,te,rs])

{

//  body  of  the,  me,thod

......

}

He,re,  are,  a  fe,w  rule,s  to  re,me,mbe,r  whe,n  you  make,  the,  name,s  for  the,  me,thods  that  you  will  write,.  me,thod  name,s  are,  always  ve,rbs  or  more,  spe,cifically  ve,rb  phrase,s  (which  me,ans  you  can  use,  multiple,  words  to  name,  the,m).  the,  first  word  of  the,  me,thod  name,  should  all  be,  in  lowe,r  case,  le,tte,rs,  while,  the,  re,st  of  the,  words  should  follow  a  came,l  case,  format.  he,re,  is  an  e,xample,:

Write,me,thodname,sthisway(  )

Now,  you  should  re,me,mbe,r  that  ve,rbs  are,  use,d  for  me,thod  name,s,  and  the,y  indicate,  an  action  while,  nouns  are,  use,d  for  variable,  name,s,  and  the,y  de,note,  a  ce,rtain  attribute,.

Following  the,  syntax  for  de,claring  a  me,thod  and  following  the,  name,  conve,ntions  for  this  java  construct,  he,re,’s  a  sample,  code,  that  can  be,  use,d  to  compute,  the,  are,a  of  a  circle,.

Public  double,  compute,circle,are,a()  {  re,turn  radius  *  radius  *  math.pi;

}

### Using  constructors  in  your  code,

We,’ll  just  go  ove,r  some,  additional  de,tails  as  the,y  re,late,  to  obje,ct-orie,nte,d  programming.  as  state,d  e,arlie,r,  a  constructor  will  look  like,  a  me,thod,  and  you  can  ce,rtainly  think  of  it  and  tre,at  it  like,  a  spe,cial  kind  of  me,thod  in  java  programming.

Howe,ve,r,  a  constructor  will  still  be,  diffe,re,nt  from  a  me,thod  in  se,ve,ral  ways.  the,  name,  of  a  constructor  will  be,  the,  same,  as  the,  class  name,.  use,  the,  ke,yword  or  ope,rator  “ne,w”  to  cre,ate,  a  ne,w  instance,  of  the,  constructor  and  also  to  initialize,  it.  he,re,’s  an  e,xample,  using  the,  class  “e,mploye,e,”  and  a  varie,ty  of  ways  to  initialize,  it  in  your  code,:

E,mploye,e,  payrate,1  =  ne,w  e,mploye,e,(  );  e,mploye,e,  payrate,2  =  ne,w  e,mploye,e,(2.0);

E,mploye,e,  payrate,3  =  ne,w  e,mploye,e,(3.0,  “re,gular”);

A  constructor  will  also  implicitly  re,turn  void––that  simply  me,ans  it  doe,sn’t  have,  a  re,turn  type,.  you  can’t  put  a  re,turn  state,me,nt  inside,  the,  body  of  a  constructor  since,  it  will  be,  flagge,d  by  compile,rs  as  an  e,rror.  the,  only  way  you  can  invoke,  a  constructor  is  via  the,  use,  of  the,  “ne,w”  state,me,nt.  we,  have,  alre,ady  give,n  you  se,ve,ral  ways  how  you  can  invoke,  constructors  in  the,  sample,s  above,.

One,  final  diffe,re,nce,  is  that  constructors  can’t  be,  inhe,rite,d.  le,t’s  go  back  to  the,  e,xample,s  provide,d  above,––the,  first  line,  include,s  “e,mploye,e,(  );”––that  is  calle,d  a  de,fault  constructor.  as  you  can  se,e,,  it  has  no  parame,te,rs  whatsoe,ve,r.  the,  job  of  a  de,fault  constructor  is  to  simply  initialize,  the,  me,mbe,r  variable,s  to  a  spe,cific  de,fault  value,.  in  the,  e,xample,  above,,  the,  me,mbe,r  variable,  payrate,1  was  initialize,d  to  its  de,fault  pay  rate,  and  e,mploye,e,  status.

Can  constructors  be,  ove,rloade,d  too?  ye,s,  the,y  can.  constructors  be,have,  like,  me,thods  too,  so  that  me,ans  you  can  ove,rload  a  constructor  just  the,  same,  way  you  ove,rload  a  me,thod.  he,re,  are,  a  fe,w  e,xample,s  of  how  you  can  ove,rload  a  constructor.  we,  use,  the,  e,mploye,e,  class  and  ove,rload  it  using  diffe,re,nt  parame,te,rs.

E,mploye,e,(  )  e,mploye,e,(int  r)  e,mploye,e,(int  r,  string  b)

### How  to  initialize,  a  variable,

Now  that  we,  know  how  to  de,clare,  variable,s,  and  we,  know  the,  various  type,s  of  variable,s  that  are,  available,  to  us,  the,  ne,xt  thing  to  do  is  to  le,arn  how  to  make,  use,  of  the,se,  variable,s,  in  some,thing  calle,d  “e,xpre,ssions.”  e,xpre,ssions  are,  the,  most  use,d  building  blocks  of  a  java  program,  ge,ne,rally  me,ant  to  produce,  a  ne,w  value,  as  a  re,sult,  though  in  some,  case,s,  e,xpre,ssions  are,  use,d  to  assign  a  ne,w  value,  to  a  variable,.  ge,ne,rally,  e,xpre,ssions  are,  made,  up  of  things  such  as  value,s,  variable,s,  ope,rators,  and  me,thod  calls.  the,re,  are,  also  some,  e,xpre,ssions  that  produce,  no  re,sult,  but  rathe,r  affe,ct  anothe,r  variable,.  one,  e,xample,  would  be,  an  e,xpre,ssion  that  change,s  the,  value,  of  a  variable,  base,d  on  an  ope,ration:  the,re,  is  no  ne,w  value,  output,  and  the,re,  is  no  true,  “assignme,nt”  of  a  ne,w  value,,  but  rathe,r  the,re,  is  what  is  calle,d  a  side,  e,ffe,ct  that  re,sults  in  a  change,d  variable,  value,.

The,  "he,llo  world"  printing  program,  we,  introduce,d  raw  value,s  into  the,  print  function,  also  known  as  "hard  coding"  the,  output.  howe,ve,r,  at  this  point,  we,  should  try  to  incorporate,  what  we,  have,  le,arne,d  about  variable,s.  variable,s  ope,rate,  much  the,  same,  way  as  raw  value,s,  as  the,y  simply  re,fe,re,nce,  a  pre,viously  store,d  value,  by  the,  compute,r,  and  as  such,  the,  programme,r  can  just  use,  the,  variable,  name,  inste,ad  of  the,  value,.  in  orde,r  to  de,monstrate,  this,  le,t  us  re,me,mbe,r  the,  pre,vious  "he,llo  world"  program:

Print  ("he,llo  world")  ;

Input  ("\n\nple,ase,  pre,ss  the,  re,turn  ke,y  to  close,  this  window.")  ;

Now,  inste,ad  of  hard––coding  the,  "he,llo  world"  string,  we,  can  simply  de,clare,  it  into  a  variable,  and  have,  the,  program  output  that  variable,.  this  should  e,nd  up  looking  as:

String  =  "he,llo  world"  ;  print(string)  ;

Input  ("\n\nple,ase,  pre,ss  the,  re,turn  ke,y  to  close,  this  window.")  ;

This  should  come,  out  with  the,  same,  re,sult  as  the,  pre,vious  program,  looking  some,thing  similar  to:

He,llo  world

Ple,ase,  pre,ss  the,  re,turn  ke,y  to  close,  this  window.

# Chapte,r  3:  java  basics

### Java  de,ve,lopme,nt  kit

The,  jdk  provide,s  the,  tools  ne,e,de,d  to  build,  te,st,  and  monitor  robust  java-  anchore,d  applications.  it  allows  de,ve,lope,rs  to  acce,ss  software,  compone,nts  and  compile,  applications  during  java  programming  ope,rations.  for  e,xample,,  a  de,ve,lope,r  ne,e,ds  a  jdk-powe,re,d  e,nvironme,nt  to  be,  able,  to  write,  apple,ts  or  imple,me,nt  me,thods.

Since,  the,  jdk  more,  or  le,ss  pe,rforms  the,  ope,rations  of  a  software,  de,ve,lopme,nt  kit  (sdk),  one,  could  e,asily  confuse,  the,  scope,  and  ope,rations  of  the,  two  ite,ms.  whe,re,as  the,  jdk  is  spe,cific  to  the,  java  programming  language,,  an  sdk  has  broade,r  applicability.  but  a  jdk  still  ope,rate,s  as  a  compone,nt  of  an  sdk  in  a  program  de,ve,lopme,nt  e,nvironme,nt.  this  me,ans  that  a  de,ve,lope,r  would  still  ne,e,d  an  sdk  to  provide,  ce,rtain  tools  with  broade,r  ope,rational  characte,ristics  and  that  are,  not  available,  within  the,  jdk  domain.  de,ve,lope,r  docume,ntation  and  de,bugging  utilitie,s,  as  we,ll  as  application  se,rve,rs,  are,  some,  of  the,  crucial  tools  that  sdk  supplie,s  to  a  java  programming  e,nvironme,nt.

The,  scope,  of  jdk  de,ployme,nt  de,pe,nds  on  the,  nature,  of  the,  tasks  at  hand,  the,  supporte,d  ve,rsions,  and  the,  java  e,dition  that  is  in  use,.  for  e,xample,,  the,  java  platform,  standard  e,dition  (java  se,)  de,ve,lopme,nt  kit  is  de,signe,d  for  use,  with  the,  java  standard  e,dition.  the,  java  platform,  e,nte,rprise,  e,dition  (java  e,e,),  and  the,  java  platform,  macro  e,dition  (java  me,),  are,  the,  othe,r  major  subse,ts  of  the,  jdk.  de,tails  of  e,ach  of  the,se,  java  e,ditions  are,  de,scribe,d  in  de,tail  in  the,  subtopics  be,low.  the,  jdk  has  be,e,n  a  fre,e,  platform  since,  2007,  whe,n  it  was  uploade,d  to  the,  ope,njdk  portal.  its  ope,n-source,  status  facilitate,s  collaborations  and  allows  communitie,s  of  software,  de,ve,lope,rs  to  clone,,  hack,  or  contribute,  ide,as  for  advance,me,nts  and  upgrade,s.

### Java  se,

The,  java  se,  powe,rs  a  wide,  varie,ty  of  de,sktop  and  se,rve,r  applications.  it  supports  the,  te,sting  and  de,ployme,nt  of  the,  java  programming  language,  within  the,  de,ve,lopme,nt  e,nvironme,nt  of  the,se,  applications.  some,  of  the,  docume,ntations  associate,d  with  the,  re,ce,nt  re,le,ase,s  of  java  se,  include,  an  advance,d  manage,me,nt  console,  fe,ature,  and  a  re,vampe,d  se,t  of  java  de,ployme,nt  rule,s.  java  se,  13.0.1  is  the,  late,st  jdk  ve,rsion  for  the,  java  se,  platform  at  the,  time,  of  writing  this  book.

The,  java  se,  sdk  is  e,quippe,d  with  the,  core,  jre,  capabilitie,s  alongside,  a  portfolio  of  tools,  class  librarie,s,  and  imple,me,ntation  te,chnologie,s  that  are,  de,signe,d  for  use,  in  the,  de,ve,lopme,nt  of  de,sktop  applications.  the,se,  tools  range,  from  simple,  obje,cts  and  type,s  for  java  program  imple,me,ntations  to  advance,d  class  parame,te,rs  that  are,  suite,d  for  building  applications  with  ne,tworking  capabilitie,s  and  impe,ne,trable,  se,curity  characte,ristics.  java  programme,rs  can  also  apply  this  particular  jdk  on  the,  de,ve,lopme,nt  of  java  applications  use,d  to  simplify  acce,ss  to  database,s  or  to  e,nhance,  gui  prope,rtie,s.

### Java  e,e,

The,  java  e,e,  platform  is  an  ope,n-source,  product  that  is  de,ve,lope,d  through  the,  collaborative,  e,fforts  of  me,mbe,rs  of  the,  java  community  worldwide,.

Java  e,e,  is  close,ly  re,late,d  to  the,  java  se,  be,cause,  the,  forme,r  is  built  on  top  of  the,  latte,r.  this  particular  software,  is  inte,grate,d  with  transformative,  innovations  that  are,  de,signe,d  for  use,  in  e,nte,rprise,  solutions.  the,  fe,ature,s  and  advance,me,nts  that  are,  introduce,d  in  ne,w  re,le,ase,s  ofte,n  re,fle,ct  the,  inputs,  re,quire,me,nts,  and  re,que,sts  of  me,mbe,rs  of  the,  java  community.  the,  java  e,e,  actually  offe,rs  more,  than  twe,nty  imple,me,ntations  that  are,  compliant  with  java  programming.

The,  java  e,e,  sdk  is  me,ant  for  use,  in  the,  construction  of  applications  for  large,-scale,  ope,rations.  just  as  its  name,  sugge,sts,  this  particular  java  sdk  was  cre,ate,d  to  provide,  support  for  e,nte,rprise,  software,  solutions.  the,  jdk  fe,ature,s  a  powe,rful  api  and  runtime,  prope,rtie,s  that  java  programme,rs  re,quire,  to  build  applications  with  scalable,  and  ne,tworkable,  functionalitie,s.  de,ve,lope,rs  in  ne,e,d  of  de,ve,loping  multi-tie,re,d  applications  could  find  this  jdk  use,ful  as  we,ll.

The,  java  e,e,  8  is  the,  late,st  re,le,ase,  at  the,  time,  of  writing  this  book.  java  e,e,’s  re,vise,d  de,sign  provide,s  e,nhance,d  te,chnologie,s  for  e,nte,rprise,  solutions  as  we,ll  as  mode,rnize,d  applications  for  se,curity  and  manage,me,nt  purpose,s.  the,  re,le,ase,  fe,ature,s  se,ve,ral  advance,me,nts  that  include,d  gre,ate,r  re,st  api  capabilitie,s  provide,d  through  the,  clie,nt,  json  binding,  se,rvle,t,  and  se,curity  apis.  this  ve,rsion  also  fe,ature,s  the,  date,  and  time,  api  as  we,ll  as  the,  stre,ams  api,  according  to  information  publishe,d  in  the,  oracle,  corporate,  we,bsite,  as  of  de,ce,mbe,r  2019.

### Java  me,

The,  java  me,  platform  de,ploys  simplicity,  portability,  and  dynamism  to  provide,  a  ve,rsatile,  e,nvironme,nt  for  building  applications  for  small  gadge,ts  and  de,vice,s.  java  me,  is  known  for  having  an  outstanding  application  de,ve,lopme,nt  e,nvironme,nt,  thanks  to  its  inte,ractive,  and  use,r-frie,ndly  navigation  inte,rface,s,  as  we,ll  as  built-in  capabilitie,s  for  imple,me,nting  ne,tworking  conce,pts.  it  is  large,ly  associate,d  with  the,  inte,rne,t  of  things  (iot)  and  is  use,ful  whe,n  building  applications  de,signe,d  for  built-in  te,chnologie,s  or  conne,cte,d  de,vice,s  that  could  be,  use,d  to  inve,nt  or  imple,me,nt  futuristic  conce,pts.  java  me,’s  portability  and  runtime,  attribute,s  make,  it  suitable,  for  use,  in  software,  applications  for  we,arable,  gadge,ts,  ce,ll  phone,s,  came,ras,  se,nsors,  and  printe,rs,  among  othe,r  ite,ms  and  e,quipme,nt.

The,  java  me,  sdk  is  e,quippe,d  with  the,  re,quisite,  tools  me,ant  for  use,  within  an  inde,pe,nde,nt  e,nvironme,nt  whe,n  de,ve,loping  software,  applications,  te,sting  functionalitie,s,  and  imple,me,nting  de,vice,  simulations.  according  to  information  publishe,d  in  the,  oracle,  corporate,  we,bsite,  as  of  2019,  this  jdk  is  we,ll  suite,d  for  accommodating  “the,  conne,cte,d  limite,d  de,vice,  configuration  (cldc)”  te,chnology  alongside,  “the,  conne,cte,d  de,vice,  configuration  (cdc)”  functionality.  this  re,sults  in  a  single,  and  ve,rsatile,  e,nvironme,nt  for  de,ve,loping  applications.

The,re,  are,  se,ve,ral  othe,r  java  me,  solutions  that  support  the,  de,ployme,nt  of  the,  java  programming  language,  in  applications.  java  me,  e,mbe,dde,d  provide,s  a  runtime,  e,nvironme,nt  inte,grating  iot  capabilitie,s  in  de,vice,s,  while,  the,  java  me,  e,mbe,dde,d  clie,nt  facilitate,s  the,  construction  of  software,  solutions  that  run  and  optimize,  the,  functionality  of  built-in  programs.  java  for  mobile,  make,s  use,  of  the,  cldc  and  the,  stack  of  java  me,  de,ve,lope,r  tools  to  cre,ate,  innovative,  fe,ature,s  for  mobile,  de,vice,s.

### Java  runtime,  e,nvironme,nt

Re,me,mbe,r  that  the,re,  are,  ce,rtain  conditions  that  must  pre,vail  for  java  applications  to  run  e,fficie,ntly.  the,  jre,  contains  the,  ingre,die,nts  re,sponsible,  for  cre,ating  the,se,  re,quisite,  conditions.  this  include,s  the,  jvm  and  its  corre,sponding  file,s  and  class  attribute,s.  although  jre,  ope,rate,s  as  a  compone,nt  of  the,  jdk,  it  is  capable,  of  ope,rating  inde,pe,nde,ntly,  e,spe,cially  if  the,  tasks  are,  limite,d  to  run  rathe,r  than  build  application  instructions.

The,  jre,  le,nds  important  ope,rational  prope,rtie,s  to  diffe,re,nt  programs  in  the,  java  programming  e,cosyste,m.  for  e,xample,,  a  program  is  conside,re,d  se,lf-  containe,d  if  it  runs  an  inde,pe,nde,nt  jre,  within  it.  this  me,ans  that  a  program  doe,s  not  de,pe,nd  on  othe,r  programs  to  acce,ss  the,  jre,.  this  inde,pe,nde,nce,  make,s  it  possible,  for  a  program  to  achie,ve,  compatibility  with  diffe,re,nt  os  platforms.

### Java  virtual  machine,

The,  jvm  ope,rate,s  as  a  spe,cification  for  imple,me,nting  java  in  compute,r  programs.  it  is  the,  driving  force,  be,hind  the,  platform-inde,pe,nde,nce,  characte,ristics  of  the,  java  language,.  this  status  is  acce,ntuate,d  by  jvm’s  status  as  a  program  that  is  e,xe,cute,d  by  othe,r  programs.  the,  programs  writte,n  to  inte,ract  with  and  e,xe,cute,  the,  jvm  se,e,  it  as  a  machine,.  it  is  for  this  re,ason  that  similar  se,ts,  librarie,s,  and  inte,rface,s  are,  use,d  to  write,  java  programs  to  be,  able,  to  match  e,ve,ry  single,  jvm  imple,me,ntation  to  a  particular  os.  this  facilitate,s  the,  translation  or  inte,rpre,tation  of  java  programs  into  runtime,  instructions  in  the,  local  os,  and  the,re,by  e,liminating  the,  ne,e,d  for  platform  de,pe,nde,nce,  in  java  programming.

As  a  de,ve,lope,r,  you  must  be,  wary  of  the,  vulne,rability  your  de,ve,lopme,nt  e,nvironme,nt  and  applications  have,  to  cybe,r  attacks  and  othe,r  thre,ats.  the,  jvm  provide,s  e,nhance,d  se,curity  fe,ature,s  that  prote,ct  you  from  such  thre,ats.  the,  solid  se,curity  foundation  is  attributable,  to  its  built-in  syntax  and  structure,  limitations  that  re,side,  in  the,  ope,rational  code,s  of  class  file,s.  but  this  doe,s  not  translate,  to  limitations  on  the,  scope,  of  class  file,s  that  the,  jvm  can  accommodate,.  the,  jvm  actually  acce,pts  a  varie,ty  of  class  file,s  so  long  as  the,y  can  be,  validate,d  to  be,  safe,  and  se,cure,.  the,re,fore,,  the,  jvm  is  a  viable,  comple,me,ntary  alte,rnative,  for  de,ve,loping  software,  in  othe,r  programming  language,s.

The,  jvm  is  ofte,n  include,d  as  a  porte,d  fe,ature,  in  a  wide,  varie,ty  of  software,  applications  and  hardware,  installations.  it  is  imple,me,nte,d  through  algorithms  that  are,  de,te,rmine,d  by  oracle,  or  any  othe,r  provide,r.  as  such,  the,  jvm  provide,s  an  ope,n  imple,me,ntation  platform.  the,  jvm  actually  contains  the,  runtime,  instance,  as  the,  core,  prope,rty  that  anchors  its  command  ope,rations.  for  e,xample,,  the,  cre,ation  of  a  jvm  instance,  simply  involve,s  writing  an  instruction  in  the,  command  prompt  that,  in  turn,  runs  the,  class  prope,rtie,s  of  java.

A  java  programme,r  ne,e,ds  to  be,  familiar  with  the,  ke,y  are,as  of  jvm,  such  as  the,  classloade,r  and  the,  data  se,ction  for  runtime,  ope,rations  as  we,ll  as  the,  e,ngine,  that  is  re,sponsible,  for  e,xe,cuting  programs.  the,re,  are,  also  pe,rformance,-re,late,d  compone,nts,  such  as  the,  garbage,  colle,ctor  and  the,  he,ap  dime,nsion  tool,  that  are,  e,qually  important  to  the,  de,ployme,nt  of  the,  jvm.  the,re,  is  a  close,  affiliation  be,twe,e,n  the,  jvm  and  byte,code,s.

### Byte,code,s

Byte,code,s  are,  e,sse,ntially  jvm  commands  that  are,  containe,d  in  a  class  file,  alongside,  othe,r  information  that  include,  the,  symbol  table,.  the,y  ope,rate,  as  background  language,  programs  re,sponsible,  for  facilitating  the,  inte,rpre,tation  and  e,xe,cution  of  jvm  ope,rations.  byte,code,s  are,  actually  the,  substitute,s  for  native,  code,s  be,cause,  java  doe,s  not  provide,  the,  latte,r.  the,  structure,  of  the,  jvm  re,giste,r  is  such  that  it  contains  me,thods  which,  in  turn,  accommodate,  byte,code,  stre,ams––that  is,  se,ts  of  instructions  for  the,  jvm.  in  othe,r  words,  e,ach  java  class  has  me,thods  within  it,  and  the,  class  file,  loading  proce,ss  e,xe,cute,s  a  single,  byte,code,  stre,am  for  any  give,n  me,thod.  the,  activation  of  a  me,thod  automatically  trigge,rs  a  byte,code,  the,  mome,nt  a  program  be,gins  to  run.

The,  othe,r  important  fe,ature,  of  byte,code,s  is  the,  just-in-time,  (jit)  compile,r  that  ope,rate,s  during  the,  runtime,  ope,rations  for  compiling  code,s  that  can  be,  e,xe,cute,d.  the,  fe,ature,  actually  e,xists  as  a  hotspot  jit  compile,r  within  the,  jvm  e,cosyste,m.  it  e,xe,cute,s  code,s  concurre,ntly  with  the,  java  runtime,  ope,rations  be,cause,  it  has  the,  ability  to  pe,rform  at  optimize,d  le,ve,ls  and  the,  fle,xibility  to  scale,  and  accommodate,  growing  traffic  of  instructions.

Pre,viously,  the,  jit  compile,r  re,quire,d  fre,que,nt  tuning  to  rid  it  of  re,dundant  programs  and  re,fre,sh  its  me,mory.  tuning  was  a  ne,ce,ssary  proce,dure,  that  e,nsure,d  the,  jit  compile,r  de,live,re,d  optimum  pe,rformance,.  howe,ve,r,  the,  fre,que,nt  upgrade,s  in  the,  ne,we,r  ve,rsions  of  java  gradually  introduce,d  automate,d  me,mory  re,fre,shing  me,chanisms  that  e,liminate,d  the,  ne,e,d  for  re,gular  tuning.

Byte,code,s  can  be,  e,ithe,r  primitive,  type,s,  fle,xible,  type,s,  or  stack-base,d.  according  to  ve,nne,rs  (1996),  the,re,  are,  se,ve,n  parame,te,rs  of  primitive,  data,  including  byte,,  char,  double,,  float,  int,  long,  and  short.  the,  boole,an  parame,te,r  is  also  a  wide,ly  use,d  primitive,  type,,  taking  the,  tally  to  e,ight.

E,ach  of  the,  e,ight  parame,te,rs  is  me,ant  to  he,lp  de,ve,lope,rs  de,ploy  variable,s  that  can  be,  acte,d  upon  by  the,  byte,code,s.  byte,code,  stre,ams  actually  e,xpre,ss  the,se,  parame,te,rs  of  the,  primitive,  type,s  in  the,  form  of  ope,rands.  this  e,nds  up  de,signating  the,  large,r  and  more,  powe,rful  parame,te,rs  to  the,  highe,r  le,ve,ls  of  the,  byte,s’  hie,rarchy,  with  the,  smalle,r  one,s  occupying  the,  lowe,r  le,ve,ls  of  the,  hie,rarchy  in  a  de,sce,nding  orde,r.

Java  opcode,s  are,  similarly  crucial  compone,nts  of  the,  primitive,  type,s,  thanks  to  the,ir  role,  of  classifying  ope,rands.  this  role,  e,nsure,s  that  ope,rands  re,tain  the,ir  state,,  the,re,by  e,liminating  the,  ne,e,d  for  an  ope,rand  ide,ntification  inte,rface,  in  the,  jvm.  the,  jvm  is  able,  to  spe,e,d  up  proce,sse,s  be,cause,  it  is  capable,  of  multitasking  while,  accommodating  multiple,  opcode,s  that  de,live,r  domicile,  variable,s  into  stacks.  opcode,s  are,  also  use,ful  for  proce,ssing  and  de,fining  the,  value,  parame,te,rs  for  stack-base,d  byte,code,s.  according  to  ve,nne,rs  (1996),  this  could  be,  an  implicit  constant  value,,  an  ope,rand  value,,  or  a  value,  de,rive,d  from  a  constant  pool.

# Chapte,r  4:  java  e,nvironme,nt

### Writing  programs  in  e,ditors

To  write,  programs,  you  use,  a  simple,  e,ditor  such  as  note,pad,  or  you  can  use,  a  full-fle,dge,d  inte,grate,d  de,ve,lopme,nt  e,nvironme,nt  (ide,).  be,low  is  a  list  of  some,  of  the,  most  popular  ide,’s  that  are,  available,  for  java  and  some,  of  the,ir  re,le,vant  fe,ature,s.

### E,clipse,

This  ide,  has  be,e,n  around  for  quite,  a  long  time,  and  is  ve,ry  popular  and  wide,ly  use,d  amongst  the,  java  de,ve,lopme,nt  community.  some,  of  the,  core,  fe,ature,s  of  the,  ide,  are,:

![image](images/image002.png)it’s  fre,e,  and  ope,n  source,.  he,nce,  the,re,  are,  many  de,ve,lope,rs  who  ke,e,p  contributing  to  the,  ide,.

![image](images/image002.png)it  can  be,  use,d  to  de,ve,lop  applications  in  othe,r  language,s  such  as  c++,  ruby,  html5,  and  php.

![image](images/image002.png)it  has  a  rich  clie,nt  platform.

![image](images/image002.png)![image](images/image002.png)it  provide,s  the,  ability  of  re,factoring  code,.  it  he,lps  in  code,  comple,tion.

![image](images/image000.png)it  has  a  wide,  varie,ty  of  e,xte,nsions  and  plugins.

![image](images/image002.png)it  also  has  support  for  most  source,  code,  ve,rsion  control  syste,ms.

### Inte,llij  ide,a

This  is  anothe,r  popular  ide,  use,d  by  the,  java  de,ve,lopme,nt  community.  some,  of  the,  core,  fe,ature,s  of  this  ide,  are,:

![image](images/image002.png)the,  community  e,dition  is  fre,e,  and  ope,n  source,.

![image](images/image002.png)the,  paid  e,dition  provide,s  many  more,  fe,ature,s  and  allows  de,ve,lope,rs  to  build  e,nte,rprise,  applications  with  the,  java  e,nte,rprise,  e,dition.

![image](images/image002.png)![image](images/image002.png)it  provide,s  the,  ability  of  re,factoring  code,.  it  he,lps  in  code,  comple,tion.

![image](images/image000.png)it  has  a  wide,  varie,ty  of  e,xte,nsions  and  plugins.

![image](images/image002.png)it  also  has  support  for  most  source,  code,  ve,rsion  control  syste,ms.

### Ne,tbe,ans

Ne,tbe,ans  is  a  highly  re,comme,nde,d  ide,  for  be,ginne,rs  in  java  language,.  it  is  a  powe,rful  and  fast  ide,  that  supports  all  java  platforms  as  we,ll  as  mobile,  applications.  it  runs  on  a  varie,ty  of  platforms  such  as  windows,  linux,  mac  os  x,  and  solaris.  it  also  provide,s  support  for  language,s  such  as  html5,  c/c++,  and  php.

### The,  upside,s  of  java

![image](images/image100.png)java  e,pitomize,s  simplicity  in  programming,  thanks  to  its  use,r-  frie,ndly  inte,rface,  for  le,arning,  writing,  de,ployme,nt,  and  imple,me,ntation.

![image](images/image100.png)java’s  core,  archite,cture,  is  de,signe,d  to  facilitate,  e,ase,  of  inte,gration  and  conve,nie,nce,  of  use,  within  the,  de,ve,lopme,nt  e,nvironme,nt.

![image](images/image100.png)![image](images/image100.png)![image](images/image100.png)java  is  platform-inde,pe,nde,nt  and  re,adily  portable,,  making  it  suitable,  for  multitasking  and  use,  across  software,  applications.  the,  obje,ct-orie,nte,d  characte,ristics  of  java  support  the,  cre,ation  of  programs  with  standard  fe,ature,s  and  code,s  that  can  be,  re,de,ploye,d.  java’s  ne,tworking  capabilitie,s  make,  it  e,asie,r  for  programme,rs  to  cre,ate,  software,  solutions  for  share,d  computing  e,nvironme,nts.

![image](images/image100.png)the,  close,  re,lationship  be,twe,e,n  java,  the,  c++,  and  the,  c  language,s  make,s  it  e,asie,r  for  anyone,  with  knowle,dge,  of  the,  othe,r  two  language,s  to  le,arn  java.

![image](images/image100.png)java’s  automate,d  garbage,  colle,ction  provide,s  continuous  me,mory  prote,ction,  making  it  conve,nie,nt  for  programme,rs  to  e,liminate,  se,curity  vulne,rabilitie,s  while,  writing  code,s.

![image](images/image100.png)java’s  archite,cture,  is  fle,xible,  for  the,  imple,me,ntation  of  multithre,ading  programs.

![image](images/image100.png)java  is  re,adily  re,usable,,  thanks  to  the,  ability  to  re,de,ploy  classe,s  using  the,  inte,rface,  or  inhe,ritance,  fe,ature,s.

### The,  downside,s  of  java

![image](images/image100.png)since,  java  is  not  a  native,  application,  it  runs  at  lowe,r  spe,e,ds  compare,d  to  othe,r  programming  language,s.

![image](images/image100.png)java  may  also  lack  consiste,ncy  in  the,  proce,ssing  and  displaying  of  graphics.  for  e,xample,,  the,  ordinary  appe,arance,  of  the,  graphical  use,r  inte,rface,  (gui)  in  java-base,d  applications  is  quite,  diffe,re,nt  and  of  lowe,r  standards  compare,d  the,  gui  output  of  native,  software,  applications.

![image](images/image100.png)java’s  garbage,  colle,ction,  a  fe,ature,  that  manage,s  me,mory  e,fficie,ncy,  may  inte,rfe,re,  with  spe,e,d  and  pe,rformance,  whe,ne,ve,r  it  runs  as  a  background  application.

# Chapte,r  5:  obje,cts  and  classe,s

Finally,  we,  are,  going  to  look  at  classe,s  and  obje,cts;

An  obje,ct  in  java  has  got  to  have,  a  state,,  which  will  be,  store,d  in  a  fie,ld  and  a  be,havior,  indicate,d  by  a  me,thod.

A  class  is  a  sort  of  map,  a  blue,print  if  you  like,,  from  which  an  obje,ct  is  cre,ate,d.  this  is  what  a  class  looks  like,:

Public  class  dog  {  string  bre,e,d;

Int  age,c;

String  color;

Void  barking()  {

}

Void  whining()  {

}

Void  sle,e,ping()  {

}

}

A  class  may  have,  any  of  the,se,  variable,  type,s:

![image](images/image100.png)local––de,fine,d  within  a  constructor,  block,  or  me,thod.  the,  variable,  is  de,clare,d  and  the,n  initialize,d  inside,  a  me,thod  and  de,stroye,d  once,  the,  me,thod  has  e,nde,d.

![image](images/image100.png)instance,––de,fine,d  in  a  class  but  are,  outside,  a  me,thod.  initialize,d  whe,n  instantiation  of  the,  class  happe,ns  and  can  be,  acce,sse,d  from  inside,  any  constructor,  block,  or  me,thod  of  the,  class.

![image](images/image100.png)class––de,clare,d  inside,  the,  class,  use,s  the,  static  ke,yword,  and  are,  outside,  any  me,thod.

Classe,s  can  have,  multiple,  me,thods,  as  many  as  re,quire,d  to  acce,ss  all  the,  diffe,re,nt  kinds  of  value,s  in  the,  me,thod.  in  our  e,xample,  above,,  we,  had  thre,e,  me,thods––barking(),  whining(),  and  sle,e,ping().

### Constructors

E,ve,ry  class  will  have,  a  constructor;  if  you  omit  it,  a  de,fault  one,  will  be,  built  by  the,  compile,r.  whe,n  you  cre,ate,  a  ne,w  obje,ct,  at  le,ast  one,  constructor  must  be,  invoke,d.  as  a  rule,,  the,  name,  of  a  constructor  must  be,  the,  same,  as  that  of  the,  class,  and  the,re,  can  be,  as  many  constructors  as  a  class  re,quire,s.

This  is  what  a  constructor  looks  like,:  public  class  puppy  {

Public  puppy()  {

}

Public  puppy(string  name,)  {

//  this  constructor  has  a  single,  parame,te,r,  name,.

}

}

### Cre,ating  obje,cts

We,  alre,ady  know  that  a  class  is  a  kind  of  blue,print  to  cre,ate,  obje,cts  from,  so  it  goe,s  without  saying  that  the,  obje,ct  is  cre,ate,d  from  the,  class.  for  a  ne,w  obje,ct  to  be,  cre,ate,d,  we,  ne,e,d  the,  ne,w  ke,yword.

The,se,  are,  the,  thre,e,  ste,ps  ne,e,de,d  to  cre,ate,  an  obje,ct  from  a  class:  de,claration––a  variable,  must  be,  de,clare,d  with  a  name,  and  the,  obje,ct  type,  instantiation––the,  ne,w  ke,yword  is  use,d  for  cre,ating  the,  obje,ct  initialization––the,  constructor  is  calle,d,  and  this  initialize,s  the,  obje,ct.

The,  ne,xt  e,xample,  shows  how  obje,cts  are,  cre,ate,d:  public  class  puppy  {

Public  puppy(string  name,)  {

//  this  constructor  contains  a  single,  parame,te,r  calle,d  name,.  syste,m.out.println("passe,d  name,  is  :"  +  name,  );

}

Public  static  void  main(string  []args)  {

//  the,  ne,xt  state,me,nt  will  cre,ate,  an  obje,ct  calle,d  mypuppy  puppy  mypuppy  =  ne,w  puppy(  "fluffy"  );

}

}

Run  this  and  se,e,  what  happe,ns.

### Acce,ssing  instance,  variable,s  and  me,thods

Obje,cts  can  be,  use,d  whe,n  we,  want  to  acce,ss  instance,  variable,s  and  me,thods;  this  e,xample,  shows  how  we,  acce,ss  an  instance,  variable,:

/*  first  we,  cre,ate,  the,  obje,ct  */  obje,ctre,fe,re,nce,  =  ne,w  constructor();

/*  now  we,  call  our  variable,,  like,  this  */  obje,ctre,fe,re,nce,.variable,name,;

/*  now  a  class  me,thod  is  calle,d,  like,  this  */  obje,ctre,fe,re,nce,.me,thodname,();

Ne,xt,  we,  can  se,e,  the,  instance,  variable,s  and  me,thods  in  a  class  are,  acce,sse,d:  public  class  puppy  {

Int  puppyage,;

Public  puppy(string  name,)  {

//  this  constructor  contains  a  single,  parame,te,r  calle,d  name,.  syste,m.out.println("name,  chose,n  is  :"  +  name,  );

}

Public  void  se,tage,(int  age,)  {  puppyage,  =  age,;

}

Public  int  ge,tage,()  {

Syste,m.out.println("puppy's  age,  is  :"  +  puppyage,  );  re,turn  puppyage,;

}

Public  static  void  main(string[]  args)  {

/*  obje,ct  cre,ation  */

Puppy  mypuppy  =  ne,w  puppy(  "fluffy"  );

/*  now  we,  call  the,  class  me,thod  to  se,t  the,  puppy's  age,  */  mypuppy.se,tage,(2);

/*  ne,xt,  we,  call  anothe,r  class  me,thod  to  ge,t  the,  puppy's  age,  */  mypuppy.ge,tage,();

/*  we,  acce,ss  instance,  variable,  in  this  way  */  syste,m.out.println("variable,  value,  :"  +  mypuppy.puppyage,  );

}

}

Run  this  and  se,e,  what  happe,ns.

### Import  state,me,nts

One,  important  thing  to  re,me,mbe,r  is  that  paths  must  be,  fully  qualifie,d,  and  that  include,s  the,  name,s  of  the,  class  and  the,  package,.  if  not,  the,  compile,r  will  struggle,  to  load  the,  source,  code,  and  the,  classe,s.  to  qualify  a  path,  we,  ne,e,d  to  use,  import  state,me,nts  and,  in  this  e,xample,,  we,  se,e,  how  a  compile,r  loads  the,  re,que,ste,d  classe,s  into  the,  dire,ctory  we,  spe,cify:

Import  java.io.*;

Ne,xt,  we,  ne,e,d  two  classe,s  cre,ate,d,  one,  calle,d  e,mploye,e,  and  one,  calle,d  e,mploye,e,te,st.  we,  use,  the,  following  code,  to  do  this––ke,e,p  in  mind  that  e,mploye,e,  is  the,  name,  of  the,  class,  and  it  is  a  public  class.  do  this  and  the,n  save,  the,  file,,  calling  it  e,mploye,e,.java.

Also  note,  that  we,  have,  four  instance,  variable,s  he,re,––age,,  name,,  de,signation,  and  salary,  along  with  one,  constructor  that  has  be,e,n  e,xplicitly  de,fine,d  and  that  take,s  a  parame,te,r:

Public  class  e,mploye,e,  {  string  name,;

Int  age,;

String  de,signation;  double,  salary;

//  this  is  the,  constructor  of  the,  class  calle,d  e,mploye,e,  public  e,mploye,e,(string  name,)  {

This.name,  =  name,;

}

//  we,  assign  the,  age,  of  the,  e,mploye,e,  to  the,  variable,  calle,d  age,.  public  void  e,mpage,(int  e,mpage,)  {

Age,  =  e,mpage,;

}

/*  we,  assign  the,  de,signation  to  the,  variable,  calle,d  de,signation.*/  public  void  e,mpde,signation(string  e,mpde,sig)  {

De,signation  =  e,mpde,sig;

}

/*  we,  assign  the,  salary  to  the,  variable,  calle,d  salary.*/  public  void  e,mpsalary(double,  e,mpsalary)  {

Salary  =  e,mpsalary;

}

/*  print  the,  e,mploye,e,  de,tails  */  public  void  printe,mploye,e,()  {  syste,m.out.println("name,:"+  name,  );  syste,m.out.println("age,:"  +  age,  );

Syste,m.out.println("de,signation:"  +  de,signation  );

Syste,m.out.println("salary:"  +  salary);

}

}

Code,  proce,ssing  be,gins  with  a  main  me,thod,  so  you  ne,e,d  to  e,nsure,  that  your  code,  has  a  main  me,thod,  and  we,  ne,e,d  to  cre,ate,  some,  obje,cts.  we,  will  start  by  cre,ating  a  class  calle,d  e,mploye,e,te,st,  and  this  will  cre,ate,  a  couple,  of  instance,s  of  the,  class  calle,d  e,mploye,e,.  the,  me,thods  for  e,ach  obje,ct  must  be,  invoke,d  so  that  the,  value,s  may  be,  assigne,d  to  the,  variable,s.  save,  this  code,  in  e,mploye,e,te,st:

Public  class  e,mploye,e,te,st  {

Public  static  void  main(string  args[])  {

/*  cre,ate,  two  obje,cts  by  using  constructor  */

E,mploye,e,  e,mpone,  =  ne,w  e,mploye,e,("bobby  bucke,t");  e,mploye,e,  e,mptwo  =  ne,w  e,mploye,e,("she,lle,y  mary");

//  invoke,  the,  me,thods  for  e,ach  of  the,  obje,cts  we,  cre,ate,d  e,mpone,.e,mpage,(28);

E,mpone,.e,mpde,signation("se,nior  software,  de,ve,lope,r");  e,mpone,.e,mpsalary(1500);

E,mpone,.printe,mploye,e,();

E,mptwo.e,mpage,(22);  e,mptwo.e,mpde,signation("software,  de,ve,lope,r");  e,mptwo.e,mpsalary(850);  e,mptwo.printe,mploye,e,();

}

}

Now  the,  classe,s  ne,e,d  to  be,  compile,d,  and  e,mploye,e,te,st  run;  do  this  and  se,e,  what  you  ge,t.

You  should  se,e,  this:

Output

C:\>  javac  e,mploye,e,.java  c:\>  javac  e,mploye,e,te,st.java  c:\>  java  e,mploye,e,te,st  name,:  bobby  bucke,t

Age,:28

De,signation:  se,nior  software,  de,ve,lope,r  salary:1850.000

Name,:  she,lle,y  mary

Age,:22

De,signation:  software,  de,ve,lope,r  salary:850.00

# Chapte,r  6:  prope,r  working  code,  e,xample,s

Traditionally,  e,ve,ryone,'s  first  program  prints,  “he,llo  world.”  this  first  program  de,monstrate,s  how  to  cre,ate,,  save,,  and  run  a  program.  it  also  shows  the,  basic  structure,  use,d  in  all  java  programs.

He,re,'s  a  scre,e,nshot  of  the,  window  cre,ate,d  by  the,  he,llo  worldz ![image](images/image081.png)zprogram:

### Le,sson  1––java  proje,cts  and  package,s

Programs  are,  first  organize,d  by  java  proje,cts,  the,n  by  package,s  within  the,  java  proje,cts.  you'll  cre,ate,  a  java  proje,ct  for  e,ach  program  in  this  book.

Package,s  hold  program  file,s  that  are,  usually  use,d  toge,the,r.  be,cause,  the,  programs  in  this  book  will  be,  small,  most  of  the,  java  proje,cts  you  cre,ate,  will  have,  only  one,  package,.

In  this  le,sson,  you'll  cre,ate,  one,  java  proje,ct  and  one,  package,  for  your  first  program.

### Try  it

Cre,ate,  your  first  java  proje,ct,  calle,d  he,llo  world:

1.  If  e,clipse,  is  no  longe,r  ope,n:

1.  Double,-click  the,  e,clipse,  shortcut  you  cre,ate,d  on  your  de,sktop.
2.  Click  ok  to  use,  your  java  work  folde,r  as  your  workspace,.

1.  Right-click  in  the,  package,  e,xplore,r  pane,  and  choose,  ne,w/java  proje,ct.
2.  Name,  the,  java  proje,ct  he,llo  world,  and  se,le,ct  use,  de,fault  jre,  if  it  is  1.7  or  highe,r,  the,n  click  ne,xt,  as  shown  in  the,  image,  be,low.  if  the,  de,fault  jre,  is  le,ss  than  1.7,  se,le,ct  the,  option  to  use,  an  e,xe,cution  e,nvironme,nt  jre,  of  1.7  or  highe,r.

![image](images/image088.jpeg)

1.  Click  librarie,s,  the,n  click  add  e,xte,rnal  jars...,  as  shown  in  the,  image,  be,low.

![image](images/image109.jpeg)

1.  Browse,  to  and  se,le,ct  diyjava.jar,  which  you  installe,d  in  your  java  work  folde,r,  and  click  ope,n.
2.  Click  finish.

The,  package,  e,xplore,r  pane,  now  lists  one,  proje,ct  (he,llo  world)z ![image](images/image059.jpeg)zwith  the,  adde,d  jar  file,  (diyjava.jar),  as  shown  in  this  image,:

Cre,ate,  a  package,  for  your  he,llo  world  program  in  the,  he,llo  world  proje,ct:

1.  Right-click  on  the,  he,llo  world  proje,ct  and  choose,  ne,w/package,.
2.  Name,  the,  package,................................he,lloworld,

As  shown  in  the,  image,  be,low.  use,  your  own  name,  as  part  of  the,  package,  name,.  i  use,d  anne,tte,.godtland.he,lloworld  for  my  package,  name,.

![image](images/image038.jpeg)

1.  Click  finish.

The,  package,  e,xplore,r  pane,  now  shows  the,  package,  youz ![image](images/image077.jpeg)zcre,ate,d  in  your  he,llo  world  proje,ct,  as  shown  in  this  image,:

### Ke,y  points  and  more,

![image](images/image002.png)right-click  in  the,  package,  e,xplore,r  pane,  to  cre,ate,  java  proje,cts  and  package,s.

![image](images/image002.png)cre,ate,  a  diffe,re,nt  java  proje,ct  for  e,ach  program.

![image](images/image002.png)e,clipse,  will  cre,ate,  a  folde,r  on  your  compute,r  name,d  the,  same,  as  the,  java  proje,ct.  give,  your  java  proje,ct  a  name,  you  want  for  the,  folde,r  on  your  compute,r.

![image](images/image089.png)you  now  have,  a  folde,r  calle,d  he,llo  world  in  your  java  work  folde,r.

![image](images/image015.png)for  e,xample,,  capitalize,  the,  first  le,tte,r  of  e,ach  word  and  put  a  space,  be,twe,e,n  e,ach  word  like,  the,  he,llo  world  proje,ct.

![image](images/image002.png)add  diyjava.jar  to  the,  java  proje,cts  you  cre,ate,  with  the,  he,lp  of  this  book.

![image](images/image089.png)diyjava.jar  is  an  e,xte,rnal  jar  file,.

![image](images/image070.png)diyjava.jar  make,s  it  e,asy  to  write,  programs  that  print  te,xt  to  a  window.

![image](images/image002.png)organize,  your  program  file,s  into  package,s  in  java  proje,cts.

![image](images/image002.png)put  program  file,s  that  are,  usually  use,d  toge,the,r  into  one,  package,.

![image](images/image050.png)be,cause,  your  programs  will  be,  small,  most  of  your  programs  will  have,  only  one,  package,.

![image](images/image002.png)package,  name,  rule,s:

![image](images/image083.png)make,  your  package,  name,  diffe,re,nt  from  anyone,  e,lse,'s  package,  name,s.  java  programme,rs  traditionally  use,  the,ir  name,  or  busine,ss  name,  as  the,  first  part  of  the,ir  package,  name,.

![image](images/image093.png)use,  all  lowe,rcase,  le,tte,rs  with  no  space,s.

![image](images/image022.png)use,  pe,riods  be,twe,e,n  diffe,re,nt  cate,gorie,s  in  the,  package,  name,.  for  e,xample,,  if  the,  package,  name,  ide,ntifie,s  who  cre,ate,d  the,  package,  and  what  the,  package,  will  be,  use,d  for,  put  a  pe,riod  be,twe,e,n  the,  cre,ator  and  its  purpose,.

![image](images/image002.png)make,  sure,  whe,n  you  cre,ate,  the,  java  proje,cts  in  this  book  that  you  se,le,ct  the,  option  to  use,  an  e,xe,cution  e,nvironme,nt  jre,  of  javase,-1.7  or  highe,r.  once,  you  se,le,ct  this  option  for  cre,ating  a  proje,ct,  e,clipse,  will  de,fault  to  that  option  for  all  future,  java  proje,cts.

![image](images/image002.png)java  proje,cts  are,  for  e,clipse,;  package,s  are,  for  java.  be,cause,  you're,  using  e,clipse,,  you'll  use,  both  java  proje,cts  and  package,s.  if  you  we,re,  to  cre,ate,  java  programs  without  e,clipse,,  you  would  probably  use,  only  package,s.

### Le,sson  2––classe,s,  supe,rclasse,s,  and  programs

Java  programs  are,  made,  from  one,  or  more,  classe,s.  classe,s  contain  the,  actual  program  code,:  the,  instructions  that,  whe,n  run  in  se,que,nce,,  pe,rform  the,  de,sire,d  task.

![image](images/image026.png)e,ve,ry  class  must  name,  some,  othe,r  class  as  its  supe,rclass.  for  e,xample,,  programs  inte,nde,d  to  run  in  a  window  must  name,  some,  type,  of  window  class  as  its  supe,rclass.

In  this  le,sson,  you'll  cre,ate,  your  first  class:  a  program  that  runs  in  a  diywindow.

### Try  it

Cre,ate,  your  first  class  using  the,  diywindow  class  as  its  supe,rclass:

1.  Right-click  on  your  package,  in  the,  package,  e,xplore,r  pane,  and  choose,  ne,w  /  class.
2.  E,nte,r  he,lloworld  for  the,  class  name,,  as  shown  in  the,  image,  be,low.  (hint:  the,re,'s  no  space,  be,twe,e,n  “he,llo”  and  “world.”)
3.  Click  browse,  for  supe,rclass.

1.  E,nte,r  “diy”  for  the,  type,,  se,le,ct  diywindow,  as  shown  in  the,  image,  be,low,  and  click  ok.

1.  Which  me,thod  stubs  would  you  like,  to  cre,ate,?  se,le,ct  the,se,  options,  as  shown  in  the,  image,  be,low:

1.  Public  static  void  main  (string[]  args).
2.  Constructors  from  supe,rclass.
3.  It  doe,sn't  matte,r  if  the,  third  option,  inhe,rit  abstract  me,thods,  is  se,le,cte,d  or  not.

![image](images/image091.jpeg)

1.  Click  finish  to  cre,ate,  the,  class.

E,clipse,  will  cre,ate,  code,  for  a  he,lloworld  class  that  looks  like,  the,  following  listing.

You  may  find  it  e,asie,r  to  re,ad  the,  code,  listings  in  this  book  if  you  se,t  your  e,-re,ade,r  to  a  smalle,r  font  to  minimize,  word  wrapping.

Listing  1-1,  from  he,lloworld.java  package,  anne,tte,.godtland.he,lloworld;

Import  com.godtsoft.diyjava.diywindow;  public  class  he,lloworld  e,xte,nds  diywindow  {  public  he,lloworld()  {

//  todo  auto-ge,ne,rate,d  constructor  stub

}

Public  static  void  main(string[]  args)  {

//  todo  auto-ge,ne,rate,d  me,thod  stub

}

}

E,clipse,  adds  comme,nt  code,  you  don't  ne,e,d.  comme,nts  are,  line,s  that  be,gin  with  //  or  groups  of  line,s  that  be,gin  with  /*  and  e,nd  with  */.

1.  re,move,  the,  automatically-ge,ne,rate,d  comme,nt  line,s  from  this  class,  whe,re,  it  says  (code,  was  re,move,d  from  he,re,.)  in  the,  following  listing.

Listing  1-2,  from  he,lloworld.java  package,  anne,tte,.godtland.he,lloworld;  import  com.godtsoft.diyjava.diywindow;

Public  class  he,lloworld  e,xte,nds  diywindow  {  public  he,lloworld()  {

(code,  was  re,move,d  from  he,re,.)

}

Public  static  void  main(string[]  args)  {

(code,  was  re,move,d  from  he,re,.)

}

}

Re,move,  the,  automatically-ge,ne,rate,d  comme,nts  from  the,  program  code,  for  e,ve,ry  class  you  cre,ate,  for  this  book.  you'll  add  your  own  comme,nts  in  late,r  le,ssons.

Click  any  comple,te,d  listing  link  to  se,e,  how  to  comple,te,  the,  code,.  howe,ve,r,  you'll  le,arn  more,  if  you  try  to  comple,te,  the,  code,  yourse,lf  be,fore,  you  look  up  the,  answe,r.

![image](images/image021.png)the,  block  of  code,  that  starts  as  a  public  static  void  main  is  calle,d  the,  main()  me,thod.  the,  block  of  code,  that  starts  as  public  he,lloworld()  is  calle,d  the,  constructor.

Now,  add  your  first  line,s  of  code,:

1.  add  code,  to  the,  constructor  and  main()  me,thod  e,xactly  as  shown  he,re,.  change,s  to  make,  to  code,  are,  always  shown  bold  in  the,  listings.

Listing  1-3,  from  he,lloworld.java  package,  anne,tte,.godtland.he,lloworld;  import  com.godtsoft.diyjava.diywindow;

Public  class  he,lloworld  e,xte,nds  diywindow  {  public  he,lloworld()  {

Print("he,llo  world");

}

Public  static  void  main(string[]  args)  {  ne,w  he,lloworld();

}

}

1.  Pre,ss  ctrl-s  to  save,  the,  program.
2.  Click  the,  run  button,  as  shown  in  this  image,,  to  runz ![image](images/image034.jpeg)zthe,  program:

What  happe,ne,d?

A  window  should  ope,n  that  displays  “he,llo  world,”  as  shown  in  this  image,:

![image](images/image040.png)

1.  what  would  you  have,  to  change,  in  your  class  to  make,  it  say  he,llo  to  you?

Listing  1-4,  from  he,lloworld.java

...

Public  he,lloworld()  {  print("he,llo

![image](images/image037.png)

");

}

...

1.  save,  the,  program  and  run  it.

What  happe,ns  if  you  make,  a  mistake,?

1.  type,  the,  word  “print”  incorre,ctly  and  save,  the,  program.  listing  1-5,  from  he,lloworld.java

...

Public  he,lloworld()  {  print

Ttt

("he,llo  anne,tte,");

}

...

What  happe,ne,d?

Many  e,rror  indicators  appe,ar,  as  shown  in  this  image,:

![image](images/image001.jpeg)

1.  Double,-click  the,  e,rror  count  in  the,  proble,ms  pane,  of  e,clipse,  to  se,e,  the,  list  of  e,rrors  found.
2.  Double,-click  on  the,  e,rror  de,scription  in  the,  proble,ms  pane,  to  move,  your  cursor  to  the,  line,  with  the,  e,rror.
3.  ![image](images/image026.png)re,st  your  cursor  on  the,  actual  e,rror  (whe,re,  it  says  e,rror  right  he,re,  in  the,  above,  image,).  e,clipse,  will  list  ways  to  fix  the,  proble,m,  as  shown  in  the,  image,z ![image](images/image082.jpeg)zbe,low.  this  fe,ature,  of  e,clipse,  is  calle,d  quick  fix.

1.  Click  the,  quick  fix  calle,d  change,  to  “print(...).”  that  action  will  fix  the,  e,rror  for  you.

1.  save,  change,s.

All  e,rror  indicators  should  disappe,ar.  now,  print  more,:

1.  change,  the,  code,  to  make,  your  program  say  this:  he,llo,  e,arthling.

Take,  me,  to  your  le,ade,r.

Listing  1-6,  from  he,lloworld.java

...

Public  he,lloworld()  {  print

("  ");

Print("  ");

}

...

Throughout  the,  le,ssons,  unle,ss  the,re,  are,  syntax  e,rrors,  save,  change,s,  and  run  the,  program  afte,r  e,ve,ry  code,  change,.

Did  it  print  the,  corre,ct  line,s?  if  not,  fix  the,  code,  and  try  again.

1.  what  do  you  think  you  would  have,  to  print  to  put  a  blank  line,  be,twe,e,n  the,  two  se,nte,nce,s,  as  shown  be,low.  (hint:  you  want  nothing  printe,d  on  that  line,.)

He,llo,  e,arthling.

Take,  me,  to  your  le,ade,r.

Listing  1-7,  from  he,lloworld.java

...

Public  he,lloworld()  {  print("he,llo,  e,arthling.");

Print(  );

Print("take,  me,  to  your  le,ade,r.");

}

...

### Ke,y  points  and  more,

![image](images/image002.png)java  programs  are,  made,  up  of  classe,s.  e,ve,ry  program  re,quire,s  a  main()  me,thod  in  one,  of  its  classe,s.

![image](images/image079.png)the,  main()  me,thod  must  be,  writte,n  as  public  static  void  main(string[]  args).  late,r  le,ssons  will  e,xplain  what  all  those,  words  me,an.

![image](images/image002.png)multiple,  classe,s  are,  ofte,n  use,d  toge,the,r  to  cre,ate,  one,  program.  howe,ve,r,  most  of  the,  programs  in  this  book  will  be,  made,  of  only  one,  class.

![image](images/image002.png)e,ve,ry  class  must  have,  a  supe,rclass.  any  class  can  be,  use,d  as  a  supe,rclass.  you'll  cre,ate,  your  own  supe,rclass  in  a  late,r  le,sson.

![image](images/image002.png)classe,s  with  the,  same,  supe,rclass  are,  conside,re,d  to  be,  of  the,  same,  type,.  for  e,xample,,  the,  main  class  you  cre,ate,  for  e,ve,ry  program  in  this  book  will  use,  the,  diywindow  class  as  its  supe,rclass.  so  e,ve,ry  program  in  this  book  will  be,  a  type,  of  diywindow.

![image](images/image002.png)to  cre,ate,  classe,s,  right-click  in  the,  package,  e,xplore,r  pane,.

![image](images/image079.png)class  name,s  can  contain  numbe,rs,  le,tte,rs,  dollar  signs,  and  unde,rscore,s.  dollar  signs  and  unde,rscore,s  are,  usually  not  use,d.

![image](images/image027.png)![image](images/image079.png)blanks  or  pe,riods  are,n't  allowe,d  in  class  name,s.  class  name,s  cannot  start  with  a  numbe,r.

![image](images/image079.png)class  name,s  typically  start  with  an  uppe,rcase,  le,tte,r.

![image](images/image079.png)if  the,  class  name,  include,s  more,  than  one,  word,  the,  first  le,tte,r  of  e,ach  word  is  usually  uppe,rcase,,  and  the,  re,st  of  the,  le,tte,rs  are,  lowe,rcase,.

![image](images/image002.png)classe,s  can  have,  one,  or  more,  constructors.

![image](images/image092.png)the,  class  constructor  is  name,d  the,  same,  as  the,  class  and  must  be,  de,clare,d  as  public.  constructors  will  be,  e,xplaine,d  more,  in  late,r  le,ssons.

![image](images/image008.png)a  constructor  is  calle,d  by  using  ne,w,  followe,d  by  the,  name,  of  the,  constructor  and  pare,nthe,se,s.  for  e,xample,,  ne,w  he,lloword()  in  the,  main()  me,thod  calls  the,  he,lloworld  constructor.

![image](images/image002.png)blocks  of  code,  are,  e,nclose,d  in  curly  bracke,ts,  {  },  and  e,ach  line,  of  code,  e,nds  with  a  se,micolon;

![image](images/image079.png)e,ve,ry  java  program  runs  the,  main()  me,thod  first.

![image](images/image027.png)the,  main()  me,thod  calls  the,  class  constructor  in  all  the,  programs  in  this  book.  the,re,fore,,  the,  main()  me,thod  will

Run  first,  followe,d  by  the,  class  constructor.

![image](images/image007.png)e,ach  state,me,nt  within  the,  curly  bracke,ts  is  run,  one,  at  a  time,,  in  the,  orde,r  it  appe,ars  in  the,  code,.

![image](images/image097.png)blank  line,s  be,twe,e,n  line,s  of  code,  have,  no  e,ffe,ct  on  how  the,  code,  runs.  blank  line,s  are,  adde,d  to  make,  the,  code,  e,asie,r  for  you  to  re,ad.

![image](images/image002.png)print  ()  state,me,nts  print  the,  te,xt  in  the,  pare,nthe,se,s  to  a  window.

![image](images/image007.png)e,ach  print()  state,me,nt  prints  on  a  ne,w  line,.

![image](images/image071.png)to  print  a  blank  line,,  use,  print()  with  e,mpty  pare,nthe,se,s.

![image](images/image095.png)the,  print()  me,thod  is  part  of  diywindow,  which  is  in  diyjava.jar.  that's  why  you  adde,d  the,  e,xte,rnal  jar  file,,  diyjava.jar,  to  the,  proje,ct,  and  why  you  chose,  diywindow  as  the,  supe,rclass  for  the,  he,lloworld  class.

![image](images/image002.png)comme,nts  are,  line,s  that  be,gin  with  //  or  a  group  of  line,s  that  be,gin  with  /*  and  e,nd  with  */.

Chapte,r  7:  obje,ct-orie,nte,d  programming

You  have,  le,arne,d  e,arlie,r  that  java  is  an  obje,ct-orie,nte,d  programming  language,.  as  such,  it  supports  the,  fundame,ntal  principle,s  of  this  programming  paradigm.

An  obje,ct  re,fe,rs  to  re,al  e,ntitie,s  such  as  bag,  car,  chair,  or  pe,n.  obje,ct-  orie,nte,d  programming  language,s  allow  programme,rs  to  de,sign  programs  that  use,  obje,cts  and  classe,s.  the,y  provide,  and  support  fe,ature,s  that  can  simplify  software,  de,ve,lopme,nt  and  mainte,nance,.  the,  most  important  conce,pts  of  this  programming  paradigm  are,  the,  following:

![image](images/image002.png)![image](images/image002.png)![image](images/image002.png)![image](images/image002.png)![image](images/image002.png)![image](images/image002.png)![image](images/image002.png)obje,cts  classe,s  me,thod  instance,  inhe,ritance,  abstraction  polymorphism

![image](images/image002.png)![image](images/image002.png)me,ssage,  parsing  e,ncapsulation

#### Obje,cts

In  the,  re,al  world,  you  will  e,ncounte,r  obje,cts  such  as  humans,  dogs,  cars,  and  cats.  the,se,  obje,cts  posse,ss  state,  and  be,havior.  for  instance,,  whe,n  you  think  of  a  cat,  its  state,  can  consist  of  its  bre,e,d,  color,  or  name,.  its  be,havior  may  consist  of  running,  jumping,  or  wagging  its  tail.

A  software,  obje,ct  re,se,mble,s  a  re,al-world  obje,ct  in  te,rms  of  the,se,  characte,ristics.  its  state,  is  save,d  in  fie,lds,  and  its  be,havior  is  e,xhibite,d  through  me,thods.

In  de,ve,lopme,nt,  the,  me,thods  are,  pe,rforme,d  on  an  obje,ct’s  inte,rnal  state,,  and  the,  me,thods  facilitate,  communication  be,twe,e,n  obje,cts.

#### Classe,s

Classe,s  are,  use,d  to  se,t  the,  de,finitions  for  obje,cts.  the,se,  spe,cifications  se,rve,  as  blue,prints  for  cre,ating  obje,cts.  while,  the,y  are,  not  imme,diate,ly  applie,d  whe,n  classe,s  are,  cre,ate,d,  the,  de,finitions  are,  available,  in  case,  an  obje,ct  of  the,  class  is  instantiate,d.  an  obje,ct  or  class  can  have,  multiple,  copie,s  orz ![image](images/image080.jpeg)zinstance,s  within  a  program.

Following  is  an  e,xample,  of  a  class  de,finition  for  a  class  name,d  cat:

A  class  can  have,  the,  following  type,s  of  variable,:

#### Class  variable,s

Class  variable,s  are,  those,  that  are,  de,clare,d  inside,  a  class  using  the,  static  modifie,r  and  outside,  any  me,thod.

#### Local  variable,s

Local  variable,s  are,  those,  that  are,  de,fine,d  within  the,  me,thods,  blocks,  or  constructors.  the,se,  variable,s  are,  de,clare,d  and  instantiate,d  inside,  the,  me,thod  and  are,  de,stroye,d  once,  the,  me,thod  had  be,e,n  carrie,d  out.

#### Instance,  variable,s

Instance,  variable,s  are,  those,  that  are,  inside,  a  class  but  outside,  of  the,  me,thods.  the,y  are,  initialize,d  at  the,  same,  time,  as  the,  class.  the,y  can  be,  acce,sse,d  from  a  me,thod,  block,  or  constructor  of  that  spe,cific  class.

A  class  can  contain  as  many  me,thods  as  ne,ce,ssary  to  obtain  the,  value,s  it  ne,e,ds.  for  e,xample,,  the,  cat  class  has  thre,e,  me,thods:  running(),  sle,e,ping(),  and  jumping().

#### Constructors

A  constructor  is  a  me,thod  which  is  use,d  to  initialize,  an  obje,ct.  a  class  must  contain  at  le,ast  one,  constructor.

The,  following  are,  the,  important  rule,s  for  constructors:

The,  name,  of  the,  constructor  should  match  the,  name,  of  the,  class  it  should  have,  no  e,xplicit  re,turn  type,.

#### Type,s  of  constructors

![image](images/image002.png)![image](images/image002.png)![image](images/image002.png)de,fault  or  no-arg  constructor  parame,te,rize,d  constructor  de,fault  constructor

A  constructor  without  a  parame,te,r  is  calle,d  de,fault  constructor.

![image](images/image058.jpeg)he,re,’s  the,  syntax:

#### Parame,te,rize,d  constructor

A  parame,te,rize,d  constructor  is  a  constructor  with  parame,te,rs.  it  is  use,d  to  supply  value,s  to  spe,cific  obje,cts.

The,  following  e,xample,  shows  both  type,s  of  constructors.  the,  first  one,  is  a  de,fault  constructor,  and  it  doe,sn’t  have,  anyz ![image](images/image003.jpeg)zparame,te,r.  the,  se,cond  constructor  has  one,  parame,te,r,  the,  name,.

#### Cre,ating  obje,cts

Classe,s  provide,  the,  te,mplate,  for  obje,cts.  obje,cts  are,  basically  cre,ate,d  from  a  class.  to  cre,ate,  ne,w  obje,cts,  you  will  use,  the,  ‘ne,w’  ke,yword.

The,  following  ste,ps  are,  take,n  to  cre,ate,  a  ne,w  obje,ct  from  a  class:

De,claration––this  re,fe,rs  to  a  variable,  de,claration  whe,re,  you  will  write,  the,  name,  of  the,  variable,  and  its  obje,ct  type,.

Instantiation––to  cre,ate,  a  ne,w  obje,ct;  you  will  use,  the,  ‘ne,w’  ke,yword.

Initialization––a  call  to  a  constructor  follows  the,  ‘ne,w’  ke,yword  and  initialize,s  a  ne,w  obje,ct.

The,  following  e,xample,s  show  the,  diffe,re,nt  ste,ps  take,n  toz ![image](images/image104.jpeg)zcre,ate,  a  ne,w  obje,ct  from

Class:

He,re,’s  the,  output:  passe,d  name,  is:  spotty

How  to  acce,ss  me,thods  and  instance,  variable,s

The,  cre,ate,d  obje,cts  are,  use,d  to  acce,ss  me,thods  and  instance,  variable,s.  to  acce,ss  instance,  variable,s,  you  will  use,  the,se,  ste,ps:

First,  you  must  cre,ate,  an  obje,ct:  obje,ctname,  =  ne,w  constructor();  ne,xt,  call  a  variable,  like,:  obje,ctname,.variable,name,;

To  call  a  class  me,thod:  obje,ctname,.me,thodname,();

### Java  package,

A  package,  is  simply  a  way  of  grouping  inte,rface,s  and  classe,s.  a  java  package,  se,rve,s  as  containe,r  for  classe,s.  the,  usual  basis  for  grouping  is  functionality.  the,  use,  of  package,s  facilitate,s  code,  re,usability.  whe,n  inte,rface,s  and  classe,s  are,  cate,gorize,d  into  package,s,  you  can  e,asily  acce,ss  the,m  for  use,  in  othe,r  programs.  the,  use,  of  package,s  also  he,lps  pre,ve,nt  name,  conflicts  among  classe,s  and  inte,rface,s.

To  cre,ate,  a  package,,  use,  the,  package,  state,me,nt  be,fore,  the,  package,  name,  as  the,  first  state,me,nt.

![image](images/image019.jpeg)

He,re,’s  an  e,xample,:

### Import  state,me,nt

You  may  use,  the,  import  ke,yword  to  import  package,s  to  your  source,  file,.  an  import  state,me,nt  make,s  it  e,asy  for  the,  compile,r  to  find  the,  location  of  a  class  or  source,  code,.

You  may  want  to  import  just  one,  class  from  a  package,.  youz ![image](images/image066.jpeg)zcan  use,  the,  dot  ope,rator  to  indicate,  the,

Package,  and  the,  class.  for  e,xample,:

To  import  all  classe,s  from  one,  package,,  you  can  use,  the,  wild  characte,r  *

![image](images/image046.jpeg)Afte,r  the,  dot  ope,rator.  for  e,xample,:

### Modifie,rs

Modifie,rs  are,  ke,ywords  that  alte,r  the,  me,aning  of  the,  de,finitions  in  your  code,.  java  provide,s  se,ve,ral  modifie,rs.

### Acce,ss  modifie,rs

The,  acce,ss  modifie,rs  are,  use,d  to  de,fine,  acce,ss  le,ve,ls  for  me,thods,  variable,s,  classe,s,  and  constructors.

### Private,––only  acce,ssible,  within  the,  class

Whe,n  a  me,thod,  variable,,  class,  or  constructor  is  de,clare,d  private,,  it  me,ans  that  it  is  only  available,  within  the,  class.  if  the,  class,  howe,ve,r,  has  public  ge,tte,r  me,thods,  you  may  be,  able,  to  acce,ss  a  private,  variable,  outside,  the,  class.  the,  private,  ke,yword  indicate,s  the,  highe,st  acce,ss  re,striction.  take,  note,  that  you  cannot  de,clare,  inte,rface,s  and  class  as  private,.

### Public––acce,ssible,  to  the,  world

A  me,thod,  inte,rface,,  constructor,  class,  e,tc.  that  has  be,e,n  de,fine,d  as  public  may  be,  acce,sse,d  from  othe,r  classe,s.  similarly,  blocks,  me,thods,  or  fie,lds  that  have,  be,e,n  de,fine,d  inside,  a  public  class  may  be,  acce,sse,d  from  java  class.  this  is  true,  as  long  as  the,y  are,  in  the,  same,  package,.  if  you  want  to  acce,ss  a  public  class  from  anothe,r  package,,  you  will  have,  to  import  the,  public  class.  unde,r  the,  class  inhe,ritance,  conce,pt,  subclasse,s  inhe,rit  all  public  variable,s  and  me,thods  of  a  class.

Take,  note,  that  an  application’s  main()  me,thod  will  have,  to  be,  de,clare,d  public  be,fore,  the,  java  inte,rpre,te,r  can  call  it  to  run  the,  class.

### Prote,cte,d––acce,ssible,  to  all  subclasse,s  and  package,

De,claring  a  me,thod,  variable,,  or  constructor  as  prote,cte,d  in  a  supe,rclass  make,s  it  acce,ssible,  only  to  classe,s  within  its  package,  or  to  its  subclasse,s  in  anothe,r  package,.  this  acce,ss  type,  is  use,d  if  you  want  to  allow  the,  subclass  to  use,  variable,  or  he,lpe,r  me,thods  and  pre,ve,nt  non-re,late,d  classe,s  from  using  the,m.  inte,rface,s,  as  we,ll  as  the,  fie,lds  and  me,thods  unde,r  the,m,  should  not  be,  de,clare,d  prote,cte,d,  but  fie,lds  and  me,thods  outside,  of  the,  inte,rface,  can  be,  de,clare,d  prote,cte,d.  classe,s  should  not  be,  de,clare,d  as  prote,cte,d.

De,fault:  applicable,  whe,n  no  modifie,r  is  provide,d––acce,ssible,  to  the,  package,

A  me,thod  or  variable,  that  has  be,e,n  de,clare,d  without  a  modifie,r  is  acce,ssible,  to  othe,r  classe,s  within  the,  package,.

The,  following  table,  summarize,s  the,  diffe,re,nt  acce,ss  modifie,rs  and  the,ir  e,ffe,ct:

Modifie,r

Inside,  class

Inside,  package,

Outside,  package,  by  subclass

Outside,  package,

Private,

Y

N

N

N

Public

Y

Y

Y

Y

Prote,cte,d

Y

Y

Y

N

De,fault

Y

Y

N

N

### Non-acce,ss  modifie,rs

The,  non-acce,ss  modifie,rs  can  be,  use,d  to  acce,ss  various  functionalitie,s  in  java.

### Final––use,d  to  finalize,  imple,me,ntations  of  variable,s,  me,thods,  and  classe,s

Final  variable,s

You  can  only  e,xplicitly  initialize,  a  final  variable,  once,.  whe,n  you  de,clare,  a  variable,  as  final,  you  will  ne,ve,r  be,  able,  to  re,assign  it  to  anothe,r  obje,ct.  take,  note,,  howe,ve,r,  that  you  can  still  change,  the,  data  store,d  inside,  the,  obje,ct.

This  me,ans  that  while,  you  may  change,  the,  obje,ct’s  state,,  you  will  not  be,  able,  to  change,  the,  re,fe,re,nce,.  the,  final  modifie,r  is  commonly  paire,d  with  static  to  cre,ate,  a  class  variable,  out  of  the,  constant  value,.

### Final  me,thods

The,  final  ke,yword  is  use,d  to  pre,ve,nt  a  me,thod  from  be,ing  change,d  by  subclasse,s.

### Final  classe,s

The,  final  modifie,r  is  use,d  to  pre,ve,nt  othe,r  classe,s  from  inhe,riting  any  fe,ature,  from  the,  class  de,clare,d  as  a  final  class.

### Static––use,d  to  cre,ate,  class  me,thods  or  variable,s.

You  can  use,  this  ke,yword  to  cre,ate,  a  unique,  variable,  (calle,d  a  static  variable,  or  class  variable,)  that  will  e,xist  inde,pe,nde,ntly  from  othe,r  instance,s  of  the,  class.  you  cannot  de,clare,  a  local  variable,  as  static.

You  can  also  use,  the,  static  ke,yword  to  cre,ate,  a  me,thod  (calle,d  a  static  me,thod  or  class  me,thod)  that  will  e,xist  inde,pe,nde,ntly  from  othe,r  instance,s  of  the,  class.  static  me,thods  re,cognize,  and  work  only  on  data  from  the,  argume,nts  give,n  without  conside,ring  variable,s.

You  may  acce,ss  class  me,thods  and  class  variable,s  by  writing  the,  variable,  or  me,thod  name,  afte,r  the,  class  name,  and  a  dot  (.).

### Abstract––use,d  to  cre,ate,  abstract  me,thods  or  classe,s

Abstract  class

Whe,n  a  class  is  de,clare,d  as  abstract,  it  me,ans  that  you  will  ne,ve,r  be,  able,  to  instantiate,  the,  class.  the,  only  re,ason  for  de,claring  a  class  as  abstract  is  to  e,xte,nd  the,  class.  you  cannot  de,clare,  a  class  to  be,  both  final  and  abstract,  as  you  can’t  possibly  e,xte,nd  a  final  class.  a  class  that  use,s  abstract  me,thods  will  have,  to  be,  de,clare,d  as  abstract.  failure,  to  do  so  will  re,sult  in  compile,  e,rrors.

### Abstract  me,thod

As  it  is  de,clare,d  with  no  imple,me,ntation,  an  abstract  me,thod  de,rive,s  its  me,thods  body  from  the,  subclass.  abstract  me,thods  cannot  be,  de,clare,d  as  strict  or  final.  unle,ss  it  is  also  an  abstract  class,  a  class  e,xte,nding  an  abstract  class  must  adopt  the,  abstract  me,thods  of  the,  supe,rclass.  a  class  that  contains  at  le,ast  one,  abstract  me,thod  should  be,  de,clare,d  as  an  abstract  class.  on  the,  othe,r  hand,  an  abstract  class  ne,e,d  not  have,  abstract  me,thods.

![image](images/image105.jpeg)e,xample,:

### Synchronize,d

![image](images/image047.jpeg)the,  synchronize,d  modifie,r  is  use,d  to  indicate,  that  only  one,  thre,ad  can  acce,ss  a  me,thod  at  any  give,n  time,.  you  can  use,  this  ke,yword  with  any  acce,ss  le,ve,l  modifie,r.

### Volatile,

E,xample,:

This  ke,yword  is  use,d  to  indicate,  that  a  thre,ad  acce,ssing  a  volatile,  variable,  should  me,rge,  its  private,  copy  with  the,  maste,r  copy  store,d  in  me,mory.  in  e,ffe,ct,  it  synchronize,s  all  cache,d  copie,s  of  the,  variable,  with  the,  main  me,mory.  you  may  only  use,  this  modifie,r  to  de,fine,  instance,  variable,s  of  the,  private,  or  obje,ct  type,.

![image](images/image011.jpeg)E,xample,:

### Transie,nt

The,  ke,yword  transie,nt  is  use,d  to  te,ll  the,  compile,r  to  skip  an  instance,  variable,  whe,n  it  is  se,rializing  the,  obje,ct  that  contains  the,  marke,d  variable,.

![image](images/image054.jpeg)e,xample,:

# Chapte,r  8:  de,cision  making  and  loop  control

The,  de,cision  making  structure,s  are,  use,d  in  situations  whe,re,  a  se,t  of  instructions  have,  to  be,  e,xe,cute,d  if  the,  condition  is  true,  and  anothe,r  se,t  of  instructions  have,  to  be,  e,xe,cute,d  whe,n  the,  condition  is  de,te,rmine,d  to  be,  false,.  the,re,  are,  se,ve,ral  constructs  available,  in  java  for  programming  such  sce,narios.  the,se,  structure,s  include,––

### If  state,me,nt

This  state,me,nt  is  use,d  in  situations  whe,re,  a  condition  ne,e,ds  to  be,  te,ste,d,  and  if  the,  condition  is  found  true,,  the,  block  of  code,  that  follows  this  state,me,nt  ne,e,ds  to  be,  e,xe,cute,d.  the,  syntax  for  this  construct  is––

If(condition){

/*body*/

}

Sample,  imple,me,ntation  for  this  construct  is  give,n  be,low––  public  class  ifde,mo  {

Public  static  void  main(string  args[])  {  int  i  =  10;

Int  j  =  1;  if(i>j){

Syste,m.out.print(i);

}

}

}

### If  e,lse,  state,me,nt

This  state,me,nt  is  use,d  in  situations  whe,re,  a  condition  ne,e,ds  to  be,  te,ste,d,  and  if  the,  condition  is  found  true,,  the,  block  of  code,  that  follows  this  state,me,nt  ne,e,ds  to  be,  e,xe,cute,d  e,lse,  the,  block  of  code,  that  follows  the,  e,lse,  state,me,nt  is  e,xe,cute,d.  the,  syntax  for  this  construct  is––

If(condition){

/*body*/

}

E,lse,(

/*body*/

}

Sample,  imple,me,ntation  for  this  construct  is  give,n  be,low––  public  class  ife,lse,de,mo  {

Public  static  void  main(string  args[])  {

Int  i  =  1;  int  j  =  0;  if(i>j){

Syste,m.out.print(i);

}

E,lse,{  syste,m.out.print(j);

}

}

}

### Ne,ste,d  if  state,me,nt

This  state,me,nt  is  use,d  in  situations  whe,re,  a  condition  ne,e,ds  to  be,  te,ste,d,  and  if  the,  condition  is  found  true,,  the,  block  of  code,  that  follows  this  state,me,nt  ne,e,ds  to  be,  e,xe,cute,d  e,lse,  the,  ne,xt  condition  is  te,ste,d.  if  this  condition  is  found  true,,  the,  block  of  code,  corre,sponding  to  the,  if  state,me,nt  for  this  condition  is  e,xe,cute,d.  if  none,  of  the,  conditions  are,  found  true,,  the,  block  of  code,  that  follows  the,  e,lse,  state,me,nt  is  e,xe,cute,d.  multiple,  conditions  can  be,  te,ste,d  using  the,  ne,ste,d  if  state,me,nts.  the,  syntax  for  this  construct  is––

If(condition1)  {

/*body*/

}

E,lse,  if  (condition2)  (

/*body*/

}

E,lse,  {

/*body*/

}

Sample,  imple,me,ntation  for  this  construct  is  give,n  be,low––  public  class  ne,ste,difde,mo  {

Public  static  void  main(string  args[])  {  int  i  =  0;

Int  j  =  0;  if(i>j){

Syste,m.out.print(i);

}

E,lse,  if(j>i)  {  syste,m.out.print(j);

}

E,lse,  {  syste,m.out.print("e,qual");

}

}

}

### Switch

If  you  have,  a  variable,  and  diffe,re,nt  blocks  of  code,  ne,e,d  to  be,  e,xe,cute,d  for  diffe,re,nt  value,s  of  that  variable,,  the,  ide,al  construct  that  can  be,  use,d  is  the,  switch  state,me,nt.  the,  syntax  for  this  construct  is––

Switch(variable,){  case,  <value,1>:

/*body*/  bre,ak;

Case,  <value,2>:

/*body*/  bre,ak;

Case,  <value,3>:

/*body*/  bre,ak;  de,fault:

/*body*/  bre,ak;

}

Sample,  imple,me,ntation  for  this  construct  is  give,n  be,low––  public  class  switchde,mo  {

Public  static  void  main(string  args[])  {  int  i  =  5;

Switch  (i)  {

Case,  0:  syste,m.out.print(0);  bre,ak;

Case,  2:  syste,m.out.print(2);  bre,ak;

Case,  5:  syste,m.out.print(5);  bre,ak;

De,fault:  syste,m.out.print(999);  bre,ak;

}

}

}

### Conditional  ope,rator

Java  also  supports  the,  conditional  ope,rator,  which  is  also  known  as  the,?:  ope,rator.  this  ope,rator  is  use,d  to  re,place,  the,  ‘if  e,lse,’  construct.  its  syntax  is  as  follows––

E,xpre,ssion1?  e,xpre,ssion2:  e,xpre,ssion3

He,re,,  e,xpre,ssion1  is  the,  condition  that  is  to  be,  te,ste,d.  if  the,  condition  is  true,,  e,xpre,ssion2  is  e,xe,cute,d  e,lse,  e,xpre,ssion3  is  e,xe,cute,d.

### Loop  control

The,re,  are,  se,ve,ral  situations  that  re,quire,  you  to  ite,rate,  the,  same,  se,t  of  instructions  a  numbe,r  of  time,s.  for  instance,,  if  you  ne,e,d  to  sort  a  se,t  of  numbe,rs,  you  will  ne,e,d  to  scan  and  re,arrange,  the,  se,t  se,ve,ral  time,s  to  ge,t  the,  de,sire,d  arrange,me,nt.  this  flow  of  e,xe,cution  is  known  as  loop  control.

Simply,  a  loop  is  a  construct  that  allows  the,  e,xe,cution  of  a  block  of  code,  many  time,s.  java  supports  se,ve,ral  constructs  that  can  be,  use,d  for  imple,me,nting  loops.  the,se,  include,  a  while,  loop,  for  loop,  and  do  while,  loop.

A  while,  loop  e,xe,cute,s  a  block  of  code,  ite,rative,ly  until  the,  condition  spe,cifie,d  for  the,  while,  loop  is  true,.  the,  mome,nt  this  condition  fails,  while,  loop  stops.

For  loop  allows  the,  programme,r  to  manipulate,  the,  condition  and  loop  variable,  in  the,  same,  construct.  the,re,fore,,  you  can  initialize,  a  loop  variable,,  incre,me,nt/de,cre,me,nt  it,  and  run  the,  loop  until  a  condition  on  this  variable,  is  true,.

Do  while,  loop  is  similar  to  while,  loop.  howe,ve,r,  in  the,  while,  loop,  the,  condition  is  che,cke,d  be,fore,  e,xe,cuting  the,  block  code,.  on  the,  othe,r  hand,  in  a  do  while,  loop,  the,  block  of  code,  is  e,xe,cute,d,  and  the,n  the,  condition  is  che,cke,d.  if  the,  condition  is  satisfie,d,  the,  loop  e,xe,cution  is  again  initiate,d  e,lse,  the,  loop  is  te,rminate,d.  it  would  not  be,  wrong  to  state,  that  the,  do  while,  loop,  once,  imple,me,nte,d,  will  e,xe,cute,  at  le,ast  once,.

### Loop  state,me,nts

The,re,  are,  two  ke,ywords  that  are,  spe,cifically  use,d  in  conne,ction  with  loops  and  are,  also  te,rme,d  as  control  state,me,nts  as  the,y  allow  transfe,r  of  control  from  one,  se,ction  of  the,  code,  to  a  diffe,re,nt  se,ction.  the,se,  ke,ywords  are,––

### Bre,ak

This  ke,yword  is  use,d  inside,  the,  loop  at  a  point  whe,re,  you  want  the,  e,xe,cution  flow  to  te,rminate,  the,  loop  and  dire,ctly  start  e,xe,cution  from  the,  first  instruction  that  appe,ars  afte,r  the,  loop.

### Continue,

This  ke,yword  is  use,d  inside,  the,  loop  at  a  point  whe,re,  the,  programme,r  wants  the,  compute,r  to  ove,rlook  the,  re,st  of  the,  loop  and  move,  the,  control  to  the,  first  state,me,nt  of  the,  loop.

In  orde,r  to  he,lp  you  unde,rstand  how  loops  are,  e,xe,cute,d,  le,t  us  take,  an  e,xample,  and  imple,me,nt  it  using  all  the,  thre,e,  type,s  of  loop  control.

### For  loop  imple,me,ntation

Public  class  forde,mo  {

Public  static  void  main(string  args[])  {

Int  []  numbe,rarray  =  {100,  300,  500,  700,  900};  for(int  i=0;  i<5;  i++)  {  syste,m.out.print(numbe,rarray[i]);  syste,m.out.print(,”");

}

Syste,m.out.print("\n");

}

}

### While,  loop  imple,me,ntation

Public  class  while,de,mo  {

Public  static  void  main(string  args[])  {

Int  []  numbe,rarray  =  {100,  300,  500,  700,  900};  int  i  =  0;

While,(i<5)  {

Syste,m.out.print(numbe,rarray[i]);  syste,m.out.print(",");

I++;

}

Syste,m.out.print("\n");

}

}

### Do  while,  loop  imple,me,ntation

Public  class  dowhile,de,mo  {

Public  static  void  main(string  args[])  {

Int  []  numbe,rarray  =  {100,  300,  500,  700,  900};  int  i  =  0;

Do  {

Syste,m.out.print(numbe,rarray[i]);  syste,m.out.print(",");

I++;

}  while,  (i<5);  syste,m.out.print("\n");

}

}

### E,nhance,d  for  loop

Java  also  supports  an  e,nhance,d  loop  structure,,  which  can  be,  use,d  for  array  e,le,me,nts.  the,  syntax  for  this  loop  construct  is––

For(de,claration  :  e,xpre,ssion)  {

/*body*/

}

The,  de,claration  part  of  the,  e,nhance,d  for  loop  is  use,d  to  de,clare,  a  variable,.  this  variable,  shall  be,  local  to  the,  ‘for  loop’  and  must  have,  the,  same,  type,  as  the,  type,  of  the,  array  e,le,me,nts.  the,  curre,nt  value,  of  the,  variable,  is  always  e,qual  to  the,  array  e,le,me,nt  that  is  be,ing  trave,rse,d  in  the,  loop.  the,  e,xpre,ssion  is  an  array  or  a  me,thod  call  that  re,turns  an  array.

Sample,  imple,me,ntation  of  the,  e,nhance,d  for  loop  has  be,e,n  give,n  be,low  -  public  class  forarrayde,mo  {

Public  static  void  main(string  args[])  {

Int  []  numbe,rarray  =  {100,  300,  500,  700,  900};  for(int  i  :  numbe,rarray  )  {

Syste,m.out.print(  i  );  syste,m.out.print(",");

}

Syste,m.out.print("\n");

}

}

### E,xce,ption  hie,rarchy

Java  has  an  inbuilt  class  name,d  java.lang.e,xce,ption  and  all  the,  e,xce,ptions  fall  unde,r  this  class.  all  the,  e,xce,ption  classe,s  are,  subclasse,s  of  this  class.  more,ove,r,  the,  throwable,  class  is  the,  supe,rclass  of  the,  e,xce,ption  class.

Anothe,r  subclass  of  the,  throwable,  class  is  the,  e,rror  class.  all  the,  e,rrors  like,  stack  ove,rflow  de,scribe,d  above,  fall  unde,r  this  e,rror  class.

The,  e,xce,ption  class  has  two  subclasse,s,  name,ly  runtime,e,xce,ption  class  and  ioe,xce,ption  class.  a  list  of  the,  me,thods,  for  which  de,finitions  are,  available,  in  java,  as  part  of  the,  throwable,  class,  is  give,n  be,low.

Public  string  ge,tme,ssage,()

Whe,n  calle,d,  this  me,ssage,  re,turns  a  de,taile,d  de,scription  of  the,  e,xce,ption  that  has  be,e,n  e,ncounte,re,d.

Public  throwable,  ge,tcause,()

This  me,thod,  whe,n  calle,d  re,turns  a  me,ssage,  that  contains  the,  cause,  of  the,  e,xce,ption.

Public  string  tostring()

This  me,thod  re,turns  the,  de,taile,d  de,scription  of  the,  e,xce,ption  concate,nate,d  with  the,  name,  of  the,  class.

Public  void  printstacktrace,()

The,  re,sult  of  tostring(),  along  with  a  trace,  of  the,  stack,  can  be,  printe,d  to  the,  standard  e,rror  stre,am,  syste,m.e,rr,  can  be,  done,  by  calling  this  me,thod.

Public  stacktrace,e,le,me,nt  []  ge,tstacktrace,()

The,re,  may  be,  some,  sce,narios  whe,re,  you  may  ne,e,d  to  acce,ss  diffe,re,nt  e,le,me,nts  of  the,  stack  trace,.  this  me,thod  re,turns  an  array,  with  e,ach  e,le,me,nt  of  the,  stack  trace,  save,d  to  diffe,re,nt  e,le,me,nts  of  the,  array.  the,  first  e,le,me,nt  of  the,  array  contains  the,  top  e,le,me,nt  of  the,  stack  trace,,  while,  the,  bottom  of  the,  stack  trace,  is  save,d  to  the,  last  e,le,me,nt  of  the,  array.

Public  throwable,  fillinstacktrace,()

Appe,nds  the,  pre,vious  information  in  the,  stack  trace,  with  the,  curre,nt  conte,nts  of  the,  stack  trace,  and  re,turns  the,  same,  as  an  array.

### Catching  e,xce,ptions

The,  standard  me,thod  to  catch  an  e,xce,ption  is  using  the,  ‘try  and  catch’  ke,ywords  along  with  the,ir  code,  imple,me,ntations.  this  try  and  catch  block  ne,e,ds  to  be,  imple,me,nte,d  in  such  a  manne,r  that  it  e,nclose,s  the,  code,  that  is  e,xpe,cte,d  to  raise,  an  e,xce,ption.  it  is  also  important  to  me,ntion  he,re,  that  the,  code,  that  is  e,xpe,cte,d  to  raise,  an  e,xce,ption  is  te,rme,d  as  prote,cte,d  code,.  the,  syntax  for  try  and  catch  block  imple,me,ntation  is  as  follows––

Try  {

/*prote,cte,d  code,*/

}catch(e,xce,ptionname,  e,xc1)  {

/*catch  code,*/

}

The,  code,  that  is  e,xpe,cte,d  to  raise,  an  e,xce,ption  is  place,d  inside,  the,  try  block.  if  the,  e,xce,ption  is  raise,d,  the,n  the,  corre,sponding  action  to  be,  pe,rforme,d  for  e,xce,ption  handling  is  imple,me,nte,d  in  the,  catch  block.  it  is  impe,rative,  for  e,ve,ry  try  block  to  e,ithe,r  have,  a  catch  block  or  a  final  block.

As  part  of  the,  catch  state,me,nt,  the,  e,xce,ption,  which  is  e,xpe,cte,d  to  be,  raise,d  ne,e,ds  to  be,  de,clare,d.  in  the,  e,ve,nt  that  an  e,xce,ption  occurs,  the,  e,xe,cution  is  transfe,rre,d  to  the,  catch  block.  if  the,  raise,d  e,xce,ption  matche,s  the,  e,xce,ption  de,fine,d  in  the,  catch  block,  the,  catch  block  is  e,xe,cute,d.

A  sample,  imple,me,ntation  of  the,  try  and  catch  block  is  give,n  be,low.  the,  code,  imple,me,nts  an  array  with  2  e,le,me,nts.  howe,ve,r,  the,  code,  trie,s  to  acce,ss  the,  third  e,le,me,nt,  which  doe,s  not  e,xist.  as  a  re,sult,  an  e,xce,ption  is  raise,d.

Import  java.io.*;

Public  class  de,moe,xce,ption  {

Public  static  void  main(string  args[])  {

Try  {

Int  arr[]  =  ne,w  int[2];

Syste,m.out.println("acce,sing  the,  3rd  e,le,me,nt  of  the,  array:"  +  arr[3]);

}catch(arrayinde,xoutofboundse,xce,ption  e,xp)  {  syste,m.out.println("catching  e,xce,ption:"  +  e,xp);

}

Syste,m.out.println("re,ache,d  outside,  catch  block");

}

}

### Imple,me,nting  multiple,  catch  blocks

A  block  of  code,  may  le,ad  to  multiple,  e,xce,ptions.  in  orde,r  to  cate,r  for  this  re,quire,me,nt,  imple,me,ntation  of  multiple,  catch  blocks  is  also  allowe,d.  the,  syntax  for  such  imple,me,ntation  is  give,n  be,low.

Try  {

/*prote,cte,d  code,*/

}catch(e,xptype,1  e,xp1)  {

/*catch  block  1*/

}catch(e,xptype,2  e,xp2)  {

/*catch  block  2*/

}catch(e,xptype,3  e,xp3)  {

/*catch  block  3*/

}

The,  syntax  shown  above,  has  illustrate,d  the,  imple,me,ntation  of  thre,e,  catch  blocks.  howe,ve,r,  you  can  imple,me,nt  as  many  catch  blocks  as  you  want.  whe,n  this  code,  is  e,xe,cute,d,  the,  prote,cte,d  is  e,xe,cute,d.  if  an  e,xce,ption  occurs,  the,  type,  of  e,xce,ption  is  matche,d  with  the,  e,xce,ption  of  the,  first  catch  block.  howe,ve,r,  if  the,  e,xce,ption  type,  doe,s  not  match,  the,  catch  block  1  is  ignore,d,  and  the,  e,xce,ption  type,  for  the,  se,cond  catch  block  is  trie,d  for  matching.  whiche,ve,r  catch  block  has  the,  same,  e,xce,ption  type,  as  that  of  the,  raise,d  e,xce,ption;  the,  corre,sponding  catch  block  is  e,xe,cute,d.

# Chapte,r  9:  adt,  data  structure,,  and  java  colle,ctions

### Abstract  data  type,  (adt)

An  abstract  data  type,  (adt)  is  a  logical  de,scription  of  the,  data  and  the,  ope,rations  that  are,  allowe,d  on  it.  adt  is  de,fine,d  as  a  use,r  point  of  vie,w  of  a  data.  adt  conce,rns  about  the,  possible,  value,s  of  the,  data  and  the,  inte,rface,  e,xpose,d  by  it.  adt  doe,s  not  conce,rn  about  the,  actual  imple,me,ntation  of  the,  data  structure,.

For  e,xample,,  a  use,r  wants  to  store,  some,  inte,ge,rs  and  find  the,ir  me,an  value,.  adt  for  this  data  structure,  will  support  two  functions,  one,  for  adding  inte,ge,rs  and  othe,r  to  ge,t  me,an  value,.  adt  for  this  data  structure,  doe,s  not  talk  about  how  e,xactly  it  will  be,  imple,me,nte,d.

![image](images/image094.jpeg)

### Data-structure,

Data  structure,s  are,  concre,te,  re,pre,se,ntations  of  data  and  are,  de,fine,d  as  a  programme,r  point  of  vie,w  of  data.  data-structure,  re,pre,se,nts  how  data  will  be,  store,d  in  me,mory.  all  data-structure,s  have,  the,ir  own  pros  and  cons.

De,pe,nding  upon  the,  type,  of  proble,m,  we,  choose,  a  data-structure,  that  is  be,st  suite,d  for  it.

For  e,xample,,  we,  can  store,  data  in  an  array,  a  linke,d-list,  stack,  que,ue,,  tre,e,,  e,tc.

Note,:  in  this  chapte,r,  we,  will  be,  studying  various  data  structure,s  and  the,ir  api.  so  that  the,  use,r  can  use,  the,m  without  knowing  the,ir  inte,rnal  imple,me,ntation.

### Java  colle,ction  frame,work

Java  programming  language,  provide,s  a  java  colle,ction  frame,work,  which  is  a  se,t  of  high  quality,  high  pe,rformance,  &  re,usable,  data-structure,s  and  algorithms.

![image](images/image086.jpeg)

The,  following  advantage,s  of  using  a  java  colle,ction  frame,work:

1.  Programme,rs  do  not  have,  to  imple,me,nt  basic  data  structure,s  and  algorithms  re,pe,ate,dly.  the,re,by  it  pre,ve,nts  the,  re,inve,ntion  of  the,

Whe,e,l.  thus,  the,  programme,r  can  de,vote,  more,  e,ffort  in  busine,ss  logic

1.  The,  java  colle,ction  frame,work  code,  is  we,ll-te,ste,d,  high  quality,  high-pe,rformance,  code,.  using  the,m  incre,ase,  the,  quality  of  the,  programs.
2.  De,ve,lopme,nt  cost  is  re,duce,d  as  basic  data  structure,s  and  algorithms  are,  imple,me,nte,d  in  the,  colle,ctions  frame,work  are,  re,use,d.
3.  E,asy  to  re,vie,w  and  unde,rstand  programs  writte,n  by  othe,r  de,ve,lope,rs  as  most  of  java  de,ve,lope,rs  use,s  the,  colle,ction  frame,work.  in  addition,  the,  colle,ction  frame,work  is  we,ll  docume,nte,d.

### Array

Array  re,pre,se,nts  a  colle,ction  of  multiple,  e,le,me,nts  of  the,  same,  datatype,s.

### Array  adt  ope,rations

Be,low  is  the,  api  of  the,  array:

1.  Adds  an  e,le,me,nt  at  the,  kth  position.  value,  can  be,  store,d  in  an  array  at  kth  position  in  o(1)  constant  time,.  we,  just  ne,e,d  to  store,  value,  at  arr[k].
2.  Re,ading  the,  value,  store,d  at  the,  kth  position.  acce,ssing  the,  value,  store,d  at  some,  inde,x  in  the,  array  is  also  o(1)  constant  time,.  we,  just  ne,e,d  to  re,ad  the,  value,  store,d  at  arr[k].
3.  Substitution  of  value,  store,d  in  the,  kth  position  with  a  ne,w  value,.  time,  comple,xity:  o(1)  constant  time,.

E,xample,:

Public  class  arrayde,mo  {

Public  static  void  main(string[]  args)  {  int[]  arr  =  ne,w  int[10];

For  (int  i  =  0;  i  <  10;  i++)

{

Arr[i]  =  i;

}

}

}

Java  standard  arrays  are,  of  fixe,d  le,ngth.  some,time,s  we,  do  not  know  how  much  me,mory  we,  ne,e,d,  so  we,  cre,ate,  a  bigge,r  size,  array.  the,re,by  wasting  space,.  if  an  array  is  alre,ady  full  and  we,  want  to  add  more,  value,s  to  it  than  we,  ne,e,d  to  cre,ate,  a  ne,w  array,  which  has  sufficie,nt  space,  and  the,n  copy  the,  old  array  to  the,  ne,w  array.  to  avoid  this  manual  re,allocation  and  copy,  we,  can  use,  arraylist  of  java  colle,ction  frame,work  or  linke,d  lists  to  store,  data.

### Arraylist  imple,me,ntation  in  java  colle,ctions

Arraylist<e,>  in  java  colle,ctions  is  a  data  structure,  which  imple,me,nts  list<e,>  inte,rface,,  which  me,ans  that  it  can  have,  duplicate,  e,le,me,nts  in  it.  arraylist  is  an  imple,me,ntation  as  a  dynamic  array  that  can  grow  or  shrink  as  ne,e,de,d.  (inte,rnally  array  is  use,d  whe,n  it  is  full  a  bigge,r  array  is  allocate,d,  and  the,  old  array  value,s  are,  copie,d  to  it).

E,xample,:

Import  java.util.arraylist;  public  class  arraylistde,mo  {

Public  static  void  main(string[]  args)  {

Arraylist<inte,ge,r>  al  =  ne,w  arraylist<inte,ge,r>();

.add(1);  //  add  1  to  the,  e,nd  of  the,  list

Al.add(2);  //  add  2  to  the,  e,nd  of  the,  list  syste,m.out.println("conte,nts  of  array:  "  +  al);  syste,m.out.println("array  size,:  "  +  al.size,());  syste,m.out.println("array  ise,mpty:  "  +  al.ise,mpty());  al.re,move,(al.size,()  -1);  //  last  e,le,me,nt  of  array  is  re,move,d.  al.re,move,all(al);  //  all  the,  e,le,me,nts  of  array  are,  re,move,d.

Syste,m.out.println("array  ise,mpty:  "  +  al.ise,mpty());

}

}

Output:

Conte,nts  of  array:  [1,  2]

Array  size,:  2

Array  ise,mpty:  false,

![image](images/image024.jpeg)array  ise,mpty:  true,

### Linke,d  list

Linke,d  lists  are,  a  dynamic  data  structure,,  and  me,mory  is  allocate,d  at  run  time,.  the,  conce,pt  of  the,  linke,d  list  is  not  to  store,  data  contiguously.  node,s  of  the,  linke,d  list  contain  a  link  that  points  to  the,  ne,xt  e,le,me,nts  in  the,  list.

Pe,rformance,-wise,  linke,d  lists  are,  slowe,r  than  arrays  be,cause,  the,re,  is  no  dire,ct  acce,ss  to  linke,d  list  e,le,me,nts.  linke,d  list  is  a  use,ful  data  structure,  whe,n  we,  do  not  know  the,  numbe,r  of  e,le,me,nts  to  be,  store,d  ahe,ad  of  time,.  the,re,  are,  many  type,s  of  linke,d  lists:  line,ar,  circular,  doubly,  doubly  circulare,,  e,tc.

### Linke,d  list  adt  ope,rations

Be,low  is  the,  api  of  linke,d  list.  inse,rt(k):  adds  k  to  the,  start  of  the,  list

Inse,rt  an  e,le,me,nt  at  the,  start  of  the,  list.  just  cre,ate,  a  ne,w  e,le,me,nt  and  move,

Pointe,rs.  so  that  this  ne,w  e,le,me,nt  be,come,s  the,  first  e,le,me,nt  of  the,  list.  this  ope,ration  will  take,  o(1)  constant  time,.

De,le,te,():  de,le,te,  the,  e,le,me,nt  at  the,  start  of  the,  list

De,le,te,  an  e,le,me,nt  at  the,  start  of  the,  list.  we,  just  ne,e,d  to  move,  one,  pointe,r.  this  ope,ration  will  also  take,  o(1)  constant  time,.

Printlist():  display  all  the,  e,le,me,nts  of  the,  list.

Start  with  the,  first  e,le,me,nt  and  the,n  follow  the,  pointe,rs.  this  ope,ration  will  take,  o(n)  time,.

Find(k):  find  the,  position  of  the,  e,le,me,nt  with  value,  k

Start  with  the,  first  e,le,me,nt  and  follow  the,  pointe,r  until  we,  ge,t  the,  value,  we,  are,  looking  for  or  re,ach  the,  e,nd  of  the,  list.  this  ope,ration  will  take,  o(n)  time,.

Note,:  binary  se,arch  doe,s  not  work  on  linke,d  lists.

Findkth(k):  find  e,le,me,nt  at  position  k

Start  from  the,  first  e,le,me,nt  and  follow  the,  links  until  you  re,ach  the,  kth  e,le,me,nt.  this  ope,ration  will  take,  o(n)  time,.

Ise,mpty():  che,ck  if  the,  numbe,r  of  e,le,me,nts  in  the,  list  are,  ze,ro.

Just  che,ck  the,  he,ad  pointe,r  of  the,  list,  if  it  is  null,  the,n  the,  list  is  e,mpty  othe,rwise,  not  e,mpty.  this  ope,ration  will  take,  o(1)  time,.

### Linke,dlist  imple,me,ntation  in  java  colle,ctions

Linke,dlist<e,>  in  by  java  colle,ctions  is  a  data  structure,  that  also  imple,me,nts  list<e,>  inte,rface,.

E,xample,:

Import  java.util.linke,dlist;  public  class  linke,dlistde,mo  {

Public  static  void  main(string[]  args)  {

Linke,dlist<inte,ge,r>  ll  =  ne,w  linke,dlist<inte,ge,r>();  ll.addfirst(2);  //  8  is  adde,d  to  the,  list

Ll.addlast(10);  //  9  is  adde,d  to  last  of  the,  list.  ll.addfirst(1);  //  7  is  adde,d  to  first  of  the,  list.  ll.addlast(11);  //  20  is  adde,d  to  last  of  the,  list  syste,m.out.println("conte,nts  of  linke,d  list:  "  +  ll);  ll.re,move,first();

Ll.re,move,last();

Syste,m.out.println("conte,nts  of  linke,d  list:  "  +  ll);

}

}

Output:

Conte,nts  of  linke,d  list:  [1,  2,  10,  11]

Conte,nts  of  linke,d  list:  [2,  10]

### Stack

![image](images/image043.jpeg)

Stack  is  a  spe,cial  kind  of  data  structure,  that  follows  the,  last-in-first-out  (lifo)  strate,gy.  this  me,ans  that  the,  e,le,me,nt  that  is  adde,d  last  will  be,  the,  first  to  be,  re,move,d.

The,  various  applications  of  the,  stack  are,:

Re,cursion:  re,cursive,  calls  are,  imple,me,nte,d  using  syste,m  stack.

1.  Postfix  e,valuation  of  the,  e,xpre,ssion.
2.  Backtracking  imple,me,nte,d  using  stack.
3.  De,pth-first  se,arch  of  tre,e,s  and  graphs.
4.  Conve,rting  a  de,cimal  numbe,r  into  a  binary  numbe,r  e,tc.

### Stack  adt  ope,rations

Push(k):  adds  value,  k  to  the,  top  of  the,  stack

Pop():  re,move,  e,le,me,nt  from  the,  top  of  the,  stack  and  re,turn  its  value,.  top():  re,turns  the,  value,  of  the,  e,le,me,nt  at  the,  top  of  the,  stack

Size,():  re,turns  the,  numbe,r  of  e,le,me,nts  in  the,  stack

Ise,mpty():  de,te,rmine,s  whe,the,r  the,  stack  is  e,mpty.  it  re,turns  true,  if  the,  stack  is  e,mpty  othe,rwise,  re,turn  false,.

Note,:  all  the,  above,  stack  ope,rations  are,  imple,me,nte,d  in  o(1)  time,  comple,xity.

### Stack  imple,me,ntation  in  java  colle,ction

The,  stack  is  imple,me,nte,d  by  calling  push  and  pop  me,thods  of  stack  <t>  class.

E,xample,:

Public  class  stackde,mo  {

Public  static  void  main(string[]  args)  {  stack<inte,ge,r>  stack  =  ne,w  stack<inte,ge,r>();  int  te,mp;

Stack.push(1);  stack.push(2);  stack.push(3);

Syste,m.out.println("stack  :  "+stack);  syste,m.out.println("stack  size,  :  "+stack.size,());  syste,m.out.println("stack  pop  :  "+stack.pop());  syste,m.out.println("stack  top  :  "+stack.pe,e,k());  syste,m.out.println("stack  ise,mpty  :  "+stack.ise,mpty());

}

}

Output:

Stack  :  [1,  2,  3]  stack  size,  :  3  stack  pop  :  3

Stack  top  :  2

Stack  ise,mpty  :  false,

Stack  is  also  imple,me,nte,d  by  calling  push  and  pop  me,thods  of  arrayde,que,<t>  class.

Jdk  provide,s  both  arrayde,que,<t>  and  stack<t>.  we,  can  use,  both  of  the,se,  classe,s.  but  the,re,  are,  some,  advantage,s  of  arrayde,que,<t>.

1.  First  re,ason  is  that  stack<t>  doe,s  not  drive,  from  colle,ction  inte,rface,.
2.  Se,cond  stack<t>  drive,s  from  ve,ctor<t>  so  random  acce,ss  is  possible,,  so  it  brake,s  abstraction  of  a  stack.
3.  Third  arrayde,que,  is  more,  e,fficie,nt  as  compare,d  to  stack<t>.

### Que,ue,

A  que,ue,  is  a  first-in-first-out  (fifo)  kind  of  data  structure,.  the,  e,le,me,nt  that  is  adde,d  to  the,  que,ue,  first  will  be,  the,  first  to  be,  re,move,d,  and  so  on.

![image](images/image039.jpeg)

Que,ue,  has  the,  following  application  use,s:

1.  acce,ss  to  share,d  re,source,s  (e,.g.,  printe,r)

2.  multiprogramming

3.  me,ssage,  que,ue,

4.  bfs,  bre,adth-first  trave,rsal  of  graph  or  tre,e,  are,  imple,me,nte,d  using  que,ue,.

Que,ue,  adt  ope,rations:

Add(k):  adds  a  ne,w  e,le,me,nt  k  to  the,  back  of  the,  que,ue,.

Re,move,():  re,move,s  an  e,le,me,nt  from  the,  front  of  the,  que,ue,  and  re,turn  its  value,.

Front():  re,turns  the,  value,  of  the,  e,le,me,nt  at  the,  front  of  the,  que,ue,.  size,():  re,turns  the,  numbe,r  of  e,le,me,nts  inside,  the,  que,ue,.

Ise,mpty():  re,turns  1  if  the,  que,ue,  is  e,mpty  othe,rwise,  re,turns  0

Note,:  all  the,  above,  que,ue,  ope,rations  are,  imple,me,nte,d  in  o(1)  time,  comple,xity.

### Que,ue,  imple,me,ntation  in  java  colle,ction

Arrayde,que,<t>  is  the,  class  imple,me,ntation  of  a  doubly  e,nde,d  que,ue,.  if  we,  use,  add(),  re,move,()  and  pe,e,k  ()  it  will  be,have,  like,  a  que,ue,.  (more,ove,r,  if  we,  use,  push(),  pop(),  and  pe,e,klast()  it  be,have,  like,  a  stack.)

E,xample,:

Import  java.util.arrayde,que,;  public  class  que,ue,de,mo  {

Public  static  void  main(string[]  args)  {

Arrayde,que,<inte,ge,r>  que,  =  ne,w  arrayde,que,<inte,ge,r>();  que,.add(1);

Que,.add(2);

Que,.add(3);  syste,m.out.println("que,ue,  :  "+que,);

Syste,m.out.println("que,ue,  size,  :  "+que,.size,());

Syste,m.out.println("que,ue,  pe,e,k  :  "+que,.pe,e,k());  syste,m.out.println("que,ue,  re,move,  :  "+que,.re,move,());  syste,m.out.println("que,ue,  ise,mpty  :  "+que,.ise,mpty());

}

}

Output:

Que,ue,  :  [1,  2,  3]  que,ue,  size,  :  3  que,ue,  pe,e,k  :  1  que,ue,  re,move,  :  1

Que,ue,  ise,mpty  :  false,

# Chapte,r  10:  file,  handling

This  chapte,r  discusse,s  the,  de,tails  of  re,ading,  writing,  cre,ating,  and  ope,ning  file,s.  the,re,  are,  a  wide,  array  of  file,  i/o  classe,s  and  me,thods  to  choose,  from.

### Re,ading  a  te,xt  file,

Re,ading  a  te,xt  file,  is  a  crucial  ability  in  java  and  has  many  practical  applications.  file,re,ade,r,  buffe,re,dre,ade,r,  and  scanne,r  are,  use,ful  classe,s  for  re,ading  a  plain  te,xt  file,  in  java.  e,ach  of  the,m  posse,ss  spe,cific  qualitie,s  that  make,  the,m  unique,ly  qualifie,d  to  handle,  ce,rtain  situations.

### Buffe,re,dre,ade,r

This  te,chnique,  re,ads  te,xt  from  a  stre,am  of  characte,r  input.  it  buffe,rs  characte,rs,  arrays,  and  rows  to  be,  re,ad  e,fficie,ntly.  you  can  spe,cify  the,  buffe,r  type,  or  use,  the,  standard  type,.  for  most  re,asons,  the,  de,fault  is  big  e,nough.  in  particular,  e,ach  re,ad  application  produce,d  from  a  re,ade,r  le,ads  the,  fundame,ntal  pe,rsonality  or  byte,  stre,am  to  make,  a  re,spe,ctive,  re,ad  application.  the,re,fore,,  it  is  advisable,  to  wrap  a  buffe,re,dre,ade,r  around  any  re,ade,r  whose,  re,ad)  (transactions,  like,  file,re,ade,rs  and  inputstre,amre,ade,rs,  can  be,  e,xpe,nsive,.

For  e,xample,:

Buffe,re,dre,ade,r  in  =  ne,w  buffe,re,dre,ade,r(re,ade,r  in,  int  size,)

### File,re,ade,r

Class  of  conve,nie,nce,  to  re,ad  characte,r  docume,nts.  this  class  '  constructors  suppose,  the,  de,fault  characte,r  format  and  the,  de,fault  byte,-buffe,r  size,  is  suitable,.

### Scanne,r

A  simple,  te,xt  scanne,r  that  use,s  re,gular  e,xpre,ssions  to  parse,  primitive,  type,s  and  strings.  a  scanne,r  use,s  a  de,limite,r  mode,l  to  bre,ak  its  e,ntry  into  toke,ns  that  suits  white,  space,  by  de,finition.  using  distinct  ne,xt  te,chnique,s,  the,  re,sulting  toke,ns  can  the,n  be,  transforme,d  into  value,s  of  distinct  kinds.

Import  java.io.file,;  import  java.util.scanne,r;

Public  class  re,adfromfile,usingscanne,r

{

Public  static  void  main(string[]  args)  throws  e,xce,ption

{

//  file,path  is  se,t  as  a  parame,te,r  now  so  that  it  can  be,  scanne,d  file,  e,xample,  =

Ne,w  file,("c:\\use,rs\\use,rname,\\de,sktop\\e,xample,.txt");

Scanne,r  e,xample,1  =  ne,w  scanne,r(file,);  while,  (e,xample,1.hasne,xtline,())  syste,m.out.println(e,xample,1.ne,xtline,());

}

}

Using  scanne,r  class  but  without  using  loops:  import  java.io.file,;

Import  java.io.file,notfounde,xce,ption;  import  java.util.scanne,r;

Public  class  e,xample,{

Public  static  void  main(string[]  args)  throws  file,notfounde,xce,ption  {

File,  e,xample,  =  ne,w  file,("c:\\use,rs\\use,rname,\\de,sktop\\e,xample,.txt");

Scanne,r  e,xample,1  =  ne,w  scanne,r(file,);

//  we,  will  use,  \\z  as  a  de,limite,r  sc.use,de,limite,r("\\z");  syste,m.out.println(e,xample,1.ne,xt());

}

}

Re,ad  a  te,xt  file,  as  string  in  java  package,  io;

Import  java.nio.file,.*;;  public  class  e,xample,{

Public  static  e,xample,(string  file,name,)throws  e,xce,ption  {

String  e,xample,1  =  "";

E,xample,1  =  ne,w  string(file,s.re,adallbyte,s(paths.ge,t(file,name,)));  re,turn  e,xample,1;

}

Public  static  void  main(string[]  args)  throws  e,xce,ption

{

String  e,xample,1  =  e,xample,("c:\\use,rs\\use,rname,\\de,sktop\\e,xample,.java");

Syste,m.out.println(e,xample,1);

}

}

### Writing  to  a  te,xt  file,

You  can  use,  one,  of  the,  write,  me,thods  to  write,  byte,s  or  line,s  to  a  file,.  write,  me,thods  include,:

![image](images/image100.png)write,(path,  byte,[],  ope,noption...)

![image](images/image100.png)write,(path,  ite,rable,<  e,xte,nds  charse,que,nce,>,  charse,t,  ope,noption...)

### Re,naming  and  de,le,ting  file,s

Re,naming

In  java,  the,re,’s  a  me,thod  calle,d  re,name,to(file,name,)  within  the,  file,  class  that  we,  can  use,  to  re,name,  a  file,.

### De,le,ting  file,s

File,s  that  are,  save,d  using  the,  java  program  will  be,  pe,rmane,ntly  re,move,d  without  moving  to  the,  trash/re,cycle,  bin.  using  java.io.file,.de,le,te,  de,le,te,s  this  abstract  pathname,  from  the,  file,  or  folde,r.  using  java.nio.file,.file,s.de,le,te,ife,xists  will  de,le,te,  a  folde,r,  if  it  occurs.  if  the,  folde,r  is  not  ope,n,  it  also  de,le,te,s  a  folde,r  liste,d  in  the,  route,.

### Advance,d  topics  in  java

Ge,ne,rics

In  any  non-trivial  software,  proje,ct,  bugs  are,  simply  a  fact  of  life,.  care,ful  planning,  programming,  and  te,sting  may  he,lp  diminish  the,ir  omnipre,se,nce,,  but  some,how  the,y  will  always  find  a  way  to  e,nte,r  your  syste,m  some,whe,re,.  this  be,come,s  e,spe,cially  appare,nt  as  ne,w  fe,ature,s  are,  introduce,d,  and  your  code,  base,'s  magnitude,  and  comple,xity  incre,ase,s.

Fortunate,ly,  it  is  e,asie,r  to  de,te,ct  some,  bugs  than  othe,rs.  compile,-time,  bugs,  for  instance,,  can  be,  ide,ntifie,d  soon;  you  can  use,  the,  compile,r's  e,rror  code,s  to  de,te,rmine,  what  the,  issue,  is  and  solve,  it,  right  the,n  and  the,re,.  runtime,  bugs,  howe,ve,r,  can  be,  much  harde,r;  the,y  do  not  always  occur  instantly,  and  whe,n  the,y  do,  the,y  may  be,  at  a  point  in  the,  program  far  apart  from  the,  true,  cause,  of  the,  proble,m.  ge,ne,rics  he,lp  stabilize,  your  software,  by  cre,ating  it  fe,asible,  at  compile,  time,  to  ide,ntify  more,  of  your  bugs.

Ge,ne,rics,  in  a  nutshe,ll,  allow  parame,te,rs  for  kinds  (classe,s  and  obje,cts)  whe,n  de,fining  course,s,  inte,rface,s,  and  te,chnique,s.  like,  the,  more,  familiar  formal  parame,te,rs  use,d  in  de,clarations  of  me,thods,  type,  parame,te,rs  provide,  you  with  distinct  outputs  to  re,-use,  the,  same,  code,.  the,  distinction  is  that  value,s  are,  the,  inputs  to  formal  parame,te,rs,  while,  kinds  are,  the,  answe,rs  to  type,  parame,te,rs.  code,  using  ge,ne,rics  has  many  advantage,s  ove,r  the,  non-  ge,ne,ric  code,.  through  the,  use,  of  ge,ne,rics,  programme,rs  can  introduce,  ge,ne,ric  algorithms  that  ope,rate,  on  distinct  kinds  of  colle,ctions,  can  be,  tailore,d,  and  are,  se,cure,  and  simple,r  to  re,ad  form.

### Ge,ne,ric  type,s

A  ge,ne,ric  form  is  a  type,s-parame,te,rize,d  ge,ne,ric  cate,gory  or  inte,rface,.  it  is  possible,  to  modify  an  e,asy  box  class  to  show  the,  ide,a.  conside,r  a  non-  ge,ne,ric  box  cate,gory  that  works  on  any  sort  of  obje,ct.  it  only  re,quire,s  to  provide,  two  te,chnique,s:  se,t),  (adding  an  ite,m  to  the,  cabine,t,  and  ge,t),  (re,trie,ving  it.  be,cause,  the,ir  me,thods  acce,pt  or  re,turn  an  obje,ct,  you  are,  fre,e,  to  pass  in  whate,ve,r  you  want,  as  long  as  it  is  not  one,  of  the,  primitive,  type,s.  the,re,  is  no  way  to  che,ck  how  the,  class  is  use,d  at  compile,  time,.  one,  portion  of  the,  software,  may  put  an  inte,ge,r  in  the,  cabine,t  and  e,xpe,ct  to  ge,t  inte,ge,rs  out  of  it,  while,  anothe,r  portion  of  the,  software,  may  e,rrone,ously  move,  through  a  string,  le,ading  in  a  mistake,  in  runtime,.

The,  se,gme,nt  of  the,  type,  parame,te,r,  de,le,gate,d  by  angle,  bracke,ts  (<  >),  displays  the,  title,  of  the,  cate,gory.  it  indicate,s  the,  parame,te,rs  of  the,  form  (also  known  as  factors  of  the,  sort)  t1,  t2,  till  t.  you  ge,ne,rate,  a  ge,ne,ric  type,  state,me,nt  by  alte,ring  the,  file,  "gove,rnme,nt  class  box"  to  "gove,rnme,nt  class  box  <t  >"  to  update,  the,  box  cate,gory  to  use,  ge,ne,rics.  this  pre,se,nts  the,  type,  variable,,  t,  which  can  be,  use,d  inside,  the,  class  anywhe,re,.  this  re,place,s  all  obje,ct  e,ve,nts  with  t.  any  non-primitive,  type,  you  spe,cify  can  be,  a  type,  variable,:  any  type,  of  class,  any  type,  of  inte,rface,,  any  type,  of  array,  or  e,ve,n  some,  othe,r  type,  variable,.  it  is  possible,  to  apply  this  same,  me,thod  to  ge,ne,ric  inte,rface,s.

Type,  de,signations  are,  single,,  uppe,r  case,  le,tte,rs  by  conve,ntion.  this  contrasts  sharply  with  the,  variable,  naming  conve,ntions  you  alre,ady  unde,rstand  about  and  with  an  e,xce,lle,nt  re,ason:  it  would  be,  hard  to  say  the,  distinction  be,twe,e,n  a  type,  variable,  and  a  normal  class  or  obje,ct  name,  without  this  conve,ntion.

The,  most  commonly  use,d  type,  parame,te,r  name,s  are,:

![image](images/image100.png)![image](images/image100.png)e,  -  e,le,me,nt  (use,d  e,xte,nsive,ly  by  the,  java  colle,ctions  frame,work)  k  -  ke,y

![image](images/image100.png)![image](images/image100.png)n  -  numbe,r  t  -  type,

![image](images/image100.png)v  -  value,

![image](images/image100.png)s,u,v,  e,tc.––2nd,  3rd,  4th  type,s

You'll  se,e,  the,se,  name,s  use,d  throughout  the,  jdk  and  the,  api.

### Invoking  and  instantiating  a  ge,ne,ric  type,

To  me,ntion  the,  ge,ne,ric  box  cate,gory  within  your  syste,m,  a  ge,ne,ric  type,  invocation  must  be,  pe,rforme,d  that  brings  t  with  a  ce,rtain  concre,te,  value,,  such  as  inte,ge,r:

Box<inte,ge,r>  inte,ge,rbox;

You  may  be,lie,ve,  that  an  invocation  of  a  ge,ne,ric  sort  is  comparable,  to  a  normal  proce,ss  invocation,  but  inste,ad  of  adding  an  asse,rtion  to  a  proce,dure,,  you  transfe,r  a  type,  argume,nt—inte,ge,r,  in  this  case,––to  the,  box  cate,gory  itse,lf.

Many  de,signe,rs  inte,rchange,ably  use,  the,  words  "type,  parame,te,r"  and  "type,  state,me,nt,"  but  not  the,  same,  de,finitions.  whe,n  coding,  to  ge,ne,rate,  a  parame,te,rize,d  type,,  one,  offe,rs  sort  argume,nts.  the,  t  in  foo  <  t  >  is,  the,re,fore,,  a  type,  parame,te,r,  and  the,  foo  <  string  >  f  string  is  a  type,  conte,ntion.  in  using  the,se,  words,  this  class  follows  this  conce,pt.

Like,  any  othe,r  state,me,nt  of  variable,,  this  software,  doe,s  not  ge,ne,rate,  a  fre,sh  ite,m  of  the,  box.  it  me,re,ly  state,s  that  inte,ge,rbox  will  have,  a  re,fe,re,nce,  to  an  "inte,ge,r  box,"  which  is  how  it  re,ads  box  <  inte,ge,r>.  a  ge,ne,ric  type,  invocation  is  usually  re,fe,rre,d  to  as  a  parame,te,rize,d  type,.

To  instantiate,  this  class,  use,  the,  ne,w  ke,yword,  as  usual,  but  place,  <inte,ge,r>  be,twe,e,n  the,  class  name,  and  the,  pare,nthe,sis:

Box<inte,ge,r>  inte,ge,rbox  =  ne,w  box<inte,ge,r>();

### The,  diamond

In  the,  late,st  ve,rsions  of  java,  you  can  re,place,  the,  type,  argume,nts  ne,e,de,d  to  invoke,  a  ge,ne,ric  class  constructor  with  an  e,mpty  se,t  of  type,  argume,nts  (<

>)  as  long  as  the,  compile,r  can  de,te,rmine,,  or  infe,r  from  the,  conte,xt,  the,  type,  argume,nts.  this  angle,  bracke,t  couple,,  <  >,  is  calle,d  “the,  diamond  loose,ly.”  for  e,xample,,  you  can  use,  the,  pre,vious  de,claration  to  ge,ne,rate,  an  instance,  of  box  <  inte,ge,r>:

Box<inte,ge,r>  inte,ge,rbox  =  ne,w  box<>();

### Ge,ne,ric  me,thods

Ge,ne,ric  te,chnique,s  are,  te,chnique,s  which  imple,me,nt  parame,te,rs  of  the,ir  own  sort.  this  is  similar  to  a  ge,ne,ric  type,  de,claration,  but  the,  scope,  of  the,  type,  parame,te,r  is  limite,d  to  the,  me,thod  in  which  it  is  de,clare,d.  in  addition  to  ge,ne,ric  class  constructors,  static  and  non-static  ge,ne,ric  te,chnique,s  are,  pe,rmitte,d.

The,  syntax  for  a  ge,ne,ric  te,chnique,  involve,s  a  list  of  parame,te,rs  of  type,  inside,  angle,  bracke,ts  that  appe,ar  be,fore,  the,  re,turn  type,  of  the,  proce,dure,.  the,  type,  parame,te,r  se,gme,nt  must  occur  be,fore,  the,  re,turn  type,  of  the,  me,thod  for  static  ge,ne,ric  te,chnique,s.  the,  util  class  involve,s,  compare,,  a  ge,ne,ric  te,chnique,  comparing  two  pair  ite,ms.

Pair<inte,ge,r,  string>  e,x1  =  ne,w  pair<>(49,  "string1");  pair<inte,ge,r,  string>  e,x2  =  ne,w  pair<>(64,  "string2");

Boole,an  comparison  =  util.<inte,ge,r,  string>compare,(e,x1,  e,x2);

### Bounde,d  type,  parame,te,rs

Some,time,s  you  want  to  limit  the,  kinds  that  can  be,  use,d  in  a  parame,te,rize,d  type,  as  form  state,me,nts.  for  instance,,  a  te,chnique,  that  works  on  figure,s  could  only  re,cognize,  numbe,r  case,s  or  its  subclasse,s.  that's  what  limit  parame,te,rs  of  the,  sort  are,  for.

List  the,  name,  of  the,  type,  parame,te,r  to  indicate,  a  de,fine,d  type,  parame,te,r,  accompanie,d  by  the,  e,xte,nsion's  ke,yword,  followe,d  by  the,  uppe,r  bound,  which  is  numbe,r  in  this  instance,.  note,  that  e,xpands  is  ge,ne,rally  use,d  in  this  conte,xt  to  me,an  e,ithe,r  "e,xte,nds"  (as  in  course,s)  or  "imple,me,nts"  (as  in  inte,rface,s).

### Multiple,  bounds

Type,  parame,te,rs  can  have,  more,  than  one,  bound.  a  type,  variable,  with  multiple,  bounds  is  a  subtype,  of  all  the,  type,s  liste,d  in  the,  bound.  if  one,  of  the,  bounds  is  a  class,  it  must  be,  spe,cifie,d  first.  for  e,xample,:

Class  x  {  /*  ...  */  }  inte,rface,  y  {  /*  ...  */  }  inte,rface,  z  {  /*  ...  */  }

Class  r  <t  e,xte,nds  x  &  y  &  z>  {  /*  ...  */  }

If  bound  x  is  not  spe,cifie,d  first,  you  ge,t  a  compile,-time,  e,rror:  class  r  <t  e,xte,nds  y  &  x  &  z>  {  /*  ...  */  }  //  compile,-time,  e,rror

# Chapte,r  11:  colle,ctions

### Functionalizing  colle,ctions

Whe,n  we,  e,xte,rnalize,  code,,  we,  e,xpose,  e,ve,ry  ste,p.  this  is  the,  hallmark  of  impe,rative,  programming.  howe,ve,r,  one,  of  the,  re,-occurring  the,me,s  of  functional  programming  is  the,  ide,a  of  doing  the,  e,xact  opposite,:  inte,rnalizing  code,.  the,  act  of  inte,rnalizing  code,  is  to  hide,  the,  de,tails  inside,  a  function.  but  functional  programming  pushe,s  this  ide,a  furthe,r  by  turning  micro-patte,rns  of  e,ve,ryday  programming  into  functions.  for  e,xample,,  ite,rating  ove,r  data,  be,  it  with  ite,rators,  for-loops,  or  while,-loops,  is  one,  of  those,  micro-patte,rns.  functional  programming  change,s  the,  way  we,  think  about  the,m.

Java’s  functionalization  e,ffort  would  not  be,  comple,te,  without  a  re,vamp  of  its  colle,ctions  library,  name,ly  the,  colle,ction,  map,  list,  and  se,t  inte,rface,s.  this  is  be,cause,  ite,ration  is  ofte,n  done,  ove,r  colle,ctions,  and  the,y  are,  the,  ve,ry  fabric  of  java  programs.  it  is  a  natural  place,  for  the,  functionalization  e,ffort  to  occur.  but  making  any  kind  of  significant  change,s,  like,  adding  ne,w  me,thods  to  the,  colle,ction  inte,rface,,  would  bre,ak  backward  compatibility  to  all  programs  writte,n  pre,-java  8.  this  include,s  not  only  the,  jdk’s  own  hie,rarchy  e,xte,nding  the,  colle,ction  inte,rface,  but  any  ope,n  or  close,d  source,  3rd  party  library  and  in-house,  classe,s.  java’s  de,signe,rs  ne,ve,r  have,  and  will  ne,ve,r  adopt  such  a  strate,gy.  ye,t  change,s  we,re,  ne,ce,ssary;  the,  library  was  introduce,d  in  1998,  e,ons  in  software,  industry  ye,ars,  and  was  showing  its  age,.

The,  motivation  for  the,  introduction  of  de,fault  me,thods  was  ushe,re,d  by  the,  ne,e,d  to  mode,rnize,  and  functionalize,  the,  colle,ctions  library.  de,fault  me,thods  are,  just  the,  right  tonic  be,cause,  the,y  pe,rmit  be,havior  to  be,  adde,d  at  the,  root  of  the,  hie,rarchy  without  disturbing  de,pe,nde,nt  classe,s.  subclasse,s  can  e,ithe,r  inhe,rit  or  ove,rride,  the,  be,havior.  unlike,  adding  ne,w  inte,rface,  me,thods,  subclasse,s  can  automatically  acce,pt  ne,w  de,fault  me,thods  without  re,compilation.  instant  compatibility  is  achie,ve,d.  de,fault  me,thods  have,  prove,n  use,ful  in  the,ir  own  right  but  owe,  the,ir  e,xiste,nce,  to  the,  ne,e,d  to  functionalize,  the,  colle,ctions  library.

A  se,cond  re,-occurring  the,me,  in  functional  programming  is  paralle,lization.  quite,  simply,  functional  programming  offe,rs  a  be,tte,r  mouse,trap  for  paralle,l  proce,ssing.  as  a  conse,que,nce,,  the,  colle,ctions  library  has  be,e,n  e,nriche,d  to  be,ne,fit  from  multi-core,  cpus  whe,n  proce,ssing  colle,ctions.  toge,the,r  with  stre,ams,  the,  colle,ctions  library  is  at  ce,nte,r  stage,  in  bringing  functional-  style,  paralle,l  proce,ssing  to  java.

Now  that  we,’ve,  studie,d  java’s  standard  functional  inte,rface,s,  we,  can  be,gin  to  apply  that  knowle,dge,  to  colle,ctions.  le,t’s  look  at  what  has  be,come,  of  the,  colle,ctions  library  in  java  8.

### Colle,ction  inte,rface,

We,  start  by  looking  at  a  brand  ne,w  de,fault  me,thod  in  the,  colle,ction  inte,rface,  available,  to  lists  and  se,ts.  this  is  the,z ![image](images/image076.jpeg)zfore,ach()  me,thod:

This  me,thod  ite,rate,s  through  the,  e,ntire,  colle,ction  le,tting  the,  consume,r  de,cide,  what  to  do  for  e,ach  e,le,me,nt.  this  is  the,  conce,pt  of  inte,rnal  ite,ration  and  a  manife,station  of  de,clarative,  programming.  the,  de,tails  of  how  to  ite,rate,  are,  not  spe,cifie,d.  this  is  in  opposition  to  e,xte,rnal  ite,ration,  whe,re,  the,  de,tails  of  how  to  ite,rate,  as  we,ll  as  what  to  do  with  e,ach  e,le,me,nt  are,  spe,cifie,d  in  code,.

We,  will  show  e,xample,s  of  the,se,  functionalize,d  colle,ction  me,thods  with  the,  slapstick  come,dy  trio  from  the,  golde,n  age,  of  hollywood  films:  larry,  moe,,  and  curly  of  the,  thre,e,  stooge,sz ![image](images/image103.jpeg)zfame,.  to  start,  le,t’s  print  the,  conte,nts  of  a  colle,ction:

The,  fore,ach()  me,thod  has  a  ve,ry  wide,  range,  of  applicability.  it  is  a  much  more,  conve,nie,nt  way  to  ite,rate,  through  colle,ctions  and  should  be,  your  de,-  facto  standard.  howe,ve,r,  be,ing  a  de,clarative,  construct,  the,re,  are,  some,  things  you  will  not  be,  able,  to  do.  most  notably,  you  cannot  change,  the,  state,  of  local  variable,s  like,  you  could  in  a  while,-loop.  algorithms  must  be,  re,-  thought  functionally.  for  now,  just  know  that  fore,ach()  is  ide,al  for  ite,rations  that  do  not  mutate,  state,.

![image](images/image096.jpeg)We,  now  look  at  anothe,r  ne,w  me,thod  available,  in  colle,ction:

The,  me,thod  re,move,if()  inte,rnalize,s  the,  e,ntire,  proce,ss  of  ite,rating,  te,sting,  and  re,moving.  it  re,quire,s  only  to  be,  told  what  the,  condition  for  re,moval  is.

Using  the,  now-familiar  pre,dicate,  functional  inte,rface,,  we,  canz ![image](images/image074.jpeg)ze,asily  figure,  out  what  kind  of  lambda  to  use,.

![image](images/image036.jpeg)To  re,place,  all  conte,nts  of  a  list,  we,  can  use,  re,place,all():

Re,place,all()  use,s  a  unaryope,rator  as  its  functional  inte,rface,,  which  is  a  function  sub  inte,rface,.

Both  re,place,if()  and  re,place,all()  are,  available,  to  all  subclasse,s  with  one,  cave,at:  the,  unde,rlying  class  must  support  re,moval,  or  an  e,xce,ption  will  be,  thrown.

The,se,  e,xample,s  show  the,  compactne,ss  of  functional  programming.  most  of  the,  work  was  done,  by  the,  function  with  the,  lambda  providing  the,  de,tails.

### Map  inte,rface,

One,  of  the,  bigge,st  irritants  of  using  lists  as  value,s  in  maps  is  the,  constant  ne,e,d  to  che,ck  for  the,  pre,se,nce,  of  the,  map  be,fore,  adding,  updating,  or  re,moving  an  e,le,me,nt.  first,  you  must  try  to  e,xtract  the,  list  and  cre,ate,  it  if  it  is  not  found.  for  e,xample,,  say  we,  have,  a  me,thod  that  update,s  a  movie,  database,  imple,me,nte,d  as  a  map.  the,  map’s  ke,y  is  the,  ye,ar  of  the,  movie,,  and  its  value,  is  a  list  of  movie,s  for  that  ye,ar.  pre,-java  8,  the,  code,  would  look  like,  this:

![image](images/image048.jpeg)

Java  8  offe,rs  a  be,tte,r  alte,rnative,  with  the,se,  de,fault  me,thods:

![image](images/image044.jpeg)

Le,t’s  start  with  the,  compute,  me,thods.  e,ach  variant  allows  the,  map’s  value,  to  be,  ge,ne,rate,d  by  the,  mapping  function.  for  compute,ifpre,se,nt()  and  compute,ifabse,nt(),  mapping  occurs  conditionally.  so  with  the,se,  me,thods,  we,  can  re,factor  the,  pre,vious  code,  e,xample,:

![image](images/image106.jpeg)

Notice,  that  the,  cre,ation  of  the,  list  is  handle,d  by  the,  compute,ifabse,nt()  lambda.  whe,n  it  is  time,  to  add  the,  movie,  to  the,  list,  via  the,  compute,()  me,thod,  the,  add()  will  ne,ve,r  throw  a  nullpointe,re,xce,ption  be,cause,  the,  list  is  guarante,e,d  to  have,  be,e,n  cre,ate,d.

In  this  case,,  using  the,  compute,ifabse,nt()  me,thod  is  ove,rkill,z ![image](images/image068.jpeg)zand  we,  would  be,  be,tte,r  off  with  putifabse,nt():

This  me,thod  is  lambda-le,ss  and  e,xpe,cts  a  value,  to  be,  give,n—not  calculate,d.  this  is  still  a  functional  style,  me,thod  e,ve,n  though  no  lambda  was  use,d.  it  prove,s  the,  point  that  you  can  e,xpre,ss  code,  functionally  without  ne,ce,ssarily  using  lambdas.

If  you  still  ne,e,d  to  e,xtract  the,  data,  you  can  use,  a  more,z ![image](images/image107.jpeg)zfunctional  approach  with  the,  ge,torde,fault()  me,thod:

You  can  also  use,  the,  me,rge,()  me,thod  as  an  alte,rnative,.  it  facilitate,s  the,  che,cking  of  the,  e,xiste,nce,  of  a  list.  in  the,  e,xample,  be,low,  if  the,  ke,y  (ye,ar)  doe,sn’t  e,xist  in  the,  map,  it  puts  the,  value,  (title,s)  on  the,  map.  if  it  doe,s  e,xist,  it  allows  a  bifunctionz ![image](images/image084.jpeg)zto  de,cide,  what  to  do  with  the,  two  lists:

![image](images/image067.jpeg)And  it  can  be,  use,d  this  way:

The,  bifunction  can  also  re,turn  null,  which  te,lls  the,  me,rge,  to  de,le,te,  the,  ke,y.

The,  take,away  is  that  we,  have,  re,move,d  the,  ove,rhe,ad  code,  of  che,cking  for  the,  e,xiste,nce,  of  an  e,le,me,nt  and  can  now  focus  on  what  re,ally  matte,rs:  de,fining  how  to  cre,ate,  the,  list  and  how  to  add  an  e,le,me,nt  to  the,  list.

The,  map  inte,rface,  has  be,e,n  e,nriche,d  with  othe,r  functional  me,thods  such  as  fore,ach(),  re,place,(),  and  re,place,all()  and  use,s  the,  same,  principle,  of  code,  inte,rnalization.  consult  the,  appe,ndix  for  the,  comple,te,  listing.

### Splite,rator

The,  colle,ctions  library  is  still  subje,ct  to  the,  same,  constraints  re,garding  concurre,nt  acce,ss.  as  always,  you  must  choose,  the,  colle,ctions  library  class  that  corre,sponds  to  your  thre,ad  safe,ty  re,quire,me,nts.  this  is  be,cause,  the,  ne,w  me,thods  shown  above,  are,  just  functional  abstractions  riding  above,  the,  same,  unde,rlying  data  structure,s.  the,se,  me,thods  are,  not  particularly  ame,nable,  to  functional  programming’s  take,  on  paralle,l  proce,ssing  be,cause,  the,y  are,  still  base,d  on  the,  notion  of  multiple,  thre,ads  mutating  the,  colle,ction  and  synchronizing  acce,ss  to  the,  unde,rlying  data.  howe,ve,r,  the,re,  e,xists  a  ne,w  java  8  abstraction  that  is  compatible,.  it  is  de,signe,d  to  ite,rate,  ove,r  data  in  paralle,l.  the,  ide,a  is  e,mbodie,d  by  the,  splite,rator  inte,rface,.  the,  pre,mise,  of  this  inte,rface,  is  to  partition  the,  data  and  handoff  chunks  to  diffe,re,nt  thre,ads.  splite,rators  can  be,  obtaine,d  from  the,  colle,ction  inte,rface,,  including  subinte,rface,s  list  and  se,t.

![image](images/image049.jpeg)Ce,ntral  to  the,  splite,rator  inte,rface,  are,  the,se,  thre,e,  me,thods:

The,  me,thod  trysplit()  partitions  the,  unde,rlying  data  in  two.  it  cre,ate,s  a  ne,w  splite,rator  with  half  the,  data  and  ke,e,ps  the,  othe,r  half  in  the,  original  instance,.  e,ach  can  be,  give,n  to  a  thre,ad  which,  in  turn,  ite,rate,s  ove,r  the,  partitione,d  data  using  fore,achre,maining().  the,  me,thod  tryadvance,()  is  a  one,-at-a-time,  variant  that  re,turns  the,  ne,xt  e,le,me,nt  or  null  if  the,  list  has  be,e,n  e,xhauste,d.

Splite,rators  do  not  handle,  paralle,l  proce,ssing  the,mse,lve,s  but  provide,  the,  abstraction  to  do  so.  he,re,’s  the,  conce,pt  in  action:

![image](images/image035.jpeg)

Give,n  a  title,  and  a  list  of  movie,s,  the,  me,thod  ismovie,inlist()  paralle,lize,s  the,  se,arch  to  de,te,rmine,  if  it  is  containe,d  in  the,  list.  it  se,ts  the,  flag  in  boole,anholde,r  to  true,  if  found.  it  obtains  a  splite,rator  instance,  from  the,  list,  splits  it  in  half,  and  handsoff  one,  half  to  e,ach  thre,ad.  the,  splitting  proce,ss  can  be,  re,pe,ate,d  if  furthe,r  thre,ads  are,  available,.

Splite,rators  can  be,  obtaine,d  from  othe,r  colle,ction  type,s  as  we,ll  as  othe,r  librarie,s  in  the,  jdk.  the,re,  are,  many  imple,me,ntations  de,signe,d  that  de,al  with  diffe,re,nt  characte,ristics,  including  finite,/infinite,,  orde,re,d/non-orde,re,d,  sorte,d/non-sorte,d,  and  mutable,/immutable,.  the,y  inhe,rit  the,  qualitie,s  of  the,ir  unde,rlying  data  structure,.

Splite,rators  are,  a  lowe,r-le,ve,l  abstraction  de,signe,d  to  give,  you  more,  fine,-  graine,d  control  ove,r  paralle,lize,d  ite,ration.  howe,ve,r,  the,  api  lacks  some,  of  the,  re,fine,me,nts  ne,e,de,d  to  imple,me,nt  functionally-frie,ndly  algorithms.  in  the,  above,  e,xample,,  we,  ne,e,de,d  to  store,  the,  state,  in  the,  boole,anholde,r  for  the,  se,arch.

### Wrap  up

This  comple,te,s  our  ove,rvie,w  of  the,  ne,w  and  improve,d  java  8  colle,ctions  library  as  we,ll  as  the,  standard  functional  inte,rface,s.  just  as  the,re,  have,  be,e,n  many  change,s  in  the,  standard  jdk  librarie,s  to  support  functional  conce,pts,  e,xpe,ct  major  change,s  from  3rd  party  apis.  but  the,  bigge,st  change,  is  ye,t  to  come,.

### Ke,y  points

The,  ne,w  package,  java.util.function  contains  a  se,t  of  functional  inte,rface,s.  the,se,  are,  groupe,d  into  four  familie,s,  e,ach  re,pre,se,nte,d  by  the,ir  arche,type,s:  consume,r,  function,  pre,dicate,,  and  supplie,r.

E,ach  family  of  functional  inte,rface,s  de,fine,s  variants  that  spe,cialize,  in  type,s  and  arity.

Functional  inte,rface,s  also  de,fine,  me,thods  that  e,nable,  functional  composition.  multiple,  disparate,  lambdas  can  be,  fuse,d  to  form  supe,r  functions  that  appe,ar  as  one,.

The,  colle,ctions  library  has  be,e,n  re,vampe,d  and  functionalize,d.  this  has  be,e,n  achie,ve,d  using  de,fault  me,thods  at  top  le,ve,ls  of  the,  hie,rarchy,  the,re,by  e,nsuring  backward  compatibility.

The,  ne,w  functional  me,thods  in  colle,ctions,  lists,  se,ts,  and  maps  have,  be,e,n  de,signe,d  with  inte,rnal  ite,ration  in  mind.  be,havioral  parame,te,rs  in  the,  form  of  lambdas  and  me,thod  re,fe,re,nce,s  are,  give,n  to  me,thods  that  ite,rate,  ove,r  colle,ctions  and  act  upon  e,ach  e,le,me,nt.

An  inte,rnal  ite,ration  is  a  form  of  de,clarative,  programming  that  is  fundame,ntal  to  functional  programming.  it  re,lie,ve,s  the,  de,ve,lope,r  from  having  to  de,scribe,  the,  “how”  to  do  it  and  focuse,s  inste,ad  on  the,  “what”  to  do.

Splite,rators  are,  de,signe,d  for  paralle,l  ite,ration  ove,r  colle,ctions.  data  is  partitione,d,  and  e,ach  chunk  is  hande,d  to  diffe,re,nt  thre,ads  for  paralle,l  proce,ssing.

A  numbe,r  is  gre,ate,r  than  one,  that  is  not  prime,.

# Conclusion

The,  jdk  is  the,  java  de,ve,lopme,nt  kit,  and  it  is  a  ne,ce,ssary  tool  re,quire,d  for  compiling,  docume,nting,  and  packaging  java  programs.  toge,the,r  with  jre,,  an  inte,rpre,te,r  or  loade,r  is  built-into  the,  jdk,  a  compile,r  calle,d  javac,  an  archive,r  (jar),  the,  javadoc  docume,nt  ge,ne,rator,  and  many  othe,r  tools  re,quire,d  for  succe,ssful  java  de,ve,lopme,nt.

The,  jre,  is  the,  java  runtime,  e,nvironme,nt.  it  is  the,  e,nvironme,nt  in  which  the,  java  byte,code,  may  be,  e,xe,cute,d,  and  it  is  use,d  for  imple,me,nting  the,  java  virtual  machine,.  the,  jre,  also  provide,s  us  with  all  the,  class  librarie,s  and  many  othe,r  support  file,s  re,quire,d  at  runtime,  by  the,  jvm.  it  is,  in  basic  te,rms,  a  software,  package,  that  provide,s  us  with  e,ve,rything  we,  ne,e,d  for  running  java  programs,  a  physical  imple,me,ntation  of  the,  java  virtual  machine,.

Jvm  stands  for  java  virtual  machine,.  the,  jvm  is  an  abstract  machine,,  a  spe,cification  that  provide,s  us  with  the,  jre,  in  which  our  byte,code,  is  e,xe,cute,d.  the,  jvm  must  follow  the,se,  notations––  spe,cification,  which  is  a  docume,nt  de,scribing  how  the,  jvm  is  imple,me,nte,d,  imple,me,ntation,  which  is  a  program  me,e,ting  the,  jvm  spe,cification  re,quire,me,nts,  and  runtime,  instance,,  which  is  the,  jvm  instance,  that  ge,ts  cre,ate,d  whe,ne,ve,r  the,  command  prompt  is  use,d  to  write,  a  java  command  and  run  a  class.

All  thre,e,  are,  ine,xtricably  linke,d,  and  e,ach  re,lie,s  on  the,  othe,rs  to  work.

With  this,  i  would  like,  to  thank  you  for  choosing  my  guide,  on  java  programming.  as  you  can  se,e,,  it  is  a  simple,  ye,t  comple,x  language,,  with  so  many  diffe,re,nt  aspe,cts  to  le,arn.  by  now,  you  should  have,  a  good  unde,rstanding  of  the,  core,  conce,pts  of  java  programming  and  how  to  use,  it.

Your  ne,xt  ste,p  is,  quite,  simply,  practice,.  and  ke,e,p  on  practicing.  you  cannot  possibly  re,ad  this  guide,  once,  and  think  that  you  know  it  all.  i  urge,  you  to  take,  your  time,  going  through  this;  follow  the,  tutorials  care,fully  and  don’t  move,  on  from  any  se,ction  until  you  fully  unde,rstand  it  and  what  it  all  me,ans.

To  he,lp  you  out,  the,re,  are,  se,ve,ral  use,ful  java  forums  to  be,  found  online,,  full  of  pe,ople,  re,ady,  and  willing  to  he,lp  you  out  and  point  you  in  the,  right  dire,ction.  the,re,  are,  also  loads  of  online,  course,s,  some,  fre,e,  and  some,  that  you  ne,e,d  to  pay  for,  but  all  of  the,m  are,  use,ful  and  can  he,lp  you  take,  your  le,arning  to  the,  ne,xt  le,ve,l.

Did  you  e,njoy  this  guide,?  i  hope,  that  it  was  all  you  wante,d  and  more,,  and  it  has  put  you  on  the,  right  path  to  ge,tting  your  dre,am  job!

I  hope,  that  you  found  my  introduction  to  compute,r  programming  he,lpful.  it’s  a  ve,ry  basic  start,  but  it  should  have,  give,n  you  some,  ide,a  as  to  how  to  be,gin.  it  should  also  have,  shown  you  that  compute,r  programming  re,ally  isn’t  all  that  difficult  and  can  be,  quite,  e,xciting,  e,spe,cially  as  you  start  to  se,e,  your  re,sults  appe,ar  on  the,  scre,e,n  and  se,e,  your  compute,r,  in  short,  doing  what  it’s  told  to  do!

If  you  found  that  this  has  give,n  you  a  good  ide,a  of  what  to  e,xpe,ct,  the,n  you  may  want  to  move,  on  to  more,  advance,d  programming  in  your  chose,n  language,.  a  word  of  warning  he,re,:  don’t  try  to  le,arn  more,  than  one,  language,  at  a  time,;  othe,rwise,,  you’ll  find  yourse,lf  in  a  muddle,.  the,  only  othe,r  pie,ce,  of  advice,  i  will  give,  you  at  this  stage,  is  to  practice,...and  ke,e,p  on  practicing.  the,  more,  you  do,  the,  more,  you’ll  le,arn,  and  the,  more,  you’ll  want  to  le,arn.

Thank  you  for  downloading  my  book;  if  you  found  it  he,lpful,  ple,ase,  conside,r  le,aving  me,  a  re,vie,w  at  amazon.com.