======
pycure
======

All about Japanese battle heroine "Pretty Cure".

Inspired by Acme::PrettyCure.

Requirements
============

- Python 3.3 or higher

- validation version 3.7.6 3.8.1 3.9.0rc1

Installation
============

::

   $ git clone https://github.com/Ricotan-naboon/pycure.git && cd pycure && python3 setup.py install
   
If You using pip, You can not get latest Packeage.

Usage
=====

Get the most recent series.

::

   $ python3
   >>> from pycure import Precure
   >>> p = Precure.now
   >>> p.title
   'ドキドキ！プリキュア'
   >>> p.girls[0].name
   '相田マナ'
   >>> p.girls[0].transform()
   みなぎる愛！ キュアハート！
   愛を無くした悲しいジコチューさん、このキュアハートがあなたのドキドキ取り戻してみせる！
   >>> p.girls[0].name
   'キュアハート'

Get from slug.

::

   $ python
   >>> from pycure import Precure
   >>> Precure.slugs
   ['', 'maxheart', 'splashstar', 'yes', 'gogo', 'fresh', 'heartcatch', 'suite', 'smile', 'dokidoki']
   >>> p = Precure["smile"]
   >>> p.girls[2].name
   '黄瀬やよい'
   >>> p.girls[2].transform()
   ピカピカピカリンジャンケンポン！ キュアピース！

Precure girls of the first series require her partner to transform.

::

   $ python
   >>> from pycure import Precure
   >>> p = Precure[""]
   >>> p.title
   'ふたりはプリキュア'
   >>> p.girls[0].name
   '美墨なぎさ'
   >>> p.girls[1].name
   '雪城ほのか'
   >>> p.girls[0].transform()
   (snip)
   pycure.girl.PartnerInvalidError
   >>> p.girls[0].transform("雪城ほのか")
   光の使者、キュアブラック！
   光の使者、キュアホワイト！
   ふたりはプリキュア！
   闇の力のしもべ達よ！
   とっととお家に帰りなさい！
   >>> p.girls[0].name
   'キュアブラック'
   >>> p.girls[1].name
   'キュアホワイト'
