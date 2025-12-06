
**Clonando Github**

```
! git clone https://github.com/renatopuga/lmabrasil-hg38.git
```

**output:**
```
Cloning into 'lmabrasil-hg38'...
remote: Enumerating objects: 226, done.
remote: Counting objects: 100% (168/168), done.
remote: Compressing objects: 100% (108/108), done.
remote: Total 226 (delta 90), reused 114 (delta 56), pack-reused 58 (from 1)
Receiving objects: 100% (226/226), 8.63 MiB | 19.47 MiB/s, done.
Resolving deltas: 100% (106/106), done.Cloning into 'lmabrasil-hg38'...
remote: Enumerating objects: 226, done.
remote: Counting objects: 100% (168/168), done.
remote: Compressing objects: 100% (108/108), done.
remote: Total 226 (delta 90), reused 114 (delta 56), pack-reused 58 (from 1)
Receiving objects: 100% (226/226), 8.63 MiB | 19.47 MiB/s, done.
Resolving deltas: 100% (106/106), done.
```
**Cortar e criar um novo arquivo chamado df_WP0017-cgi.txt**

**output:**
```
CHR	POS	REF	ALT
chr1	114716127	C	T
chr1	152304661	G	C
chr11	115209621	G	A
chr12	132140028	C	T
chr14	24119817	G	A
chr14	59727407	G	A
chr15	24675943	G	A
chr16	67616834	G	A
chr16	71389851	G	A
```

**Gerando Job ID** 

```Python
import requests
headers = {'Authorization': 'eder.fersou@gmail.com e0122907ce53686b5d72'}
payload = {'cancer_type': 'HEMATO', 'title': 'Somatic MF WP017', 'reference': 'hg38'}
r = requests.post('https://www.cancergenomeinterpreter.org/api/v1',
                headers=headers,
                files={
                        'mutations': open('df_WP017-cgi.txt', 'rb')
                        },
                data=payload)
r.json()

```

**output:**

```
20c01a79adf6a9dc4c77
```






**output:**

|index|Input ID|CHROMOSOME|POSITION|REF|ALT|CHR|POS|ALT\_TYPE|STRAND|CGI-Sample ID|CGI-Gene|CGI-Protein Change|CGI-Oncogenic Summary|CGI-Oncogenic Prediction|CGI-External oncogenic annotation|CGI-Mutation|CGI-Consequence|CGI-Transcript|CGI-STRAND|CGI-Type|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|0|input01\_1|1|114716127|C|T|chr1|114716127|snp|+|input01|NRAS|G12S|oncogenic \(predicted and annotated\)|driver \(boostDM: non-tissue-specific model\)|cgi,clinvar:177778|chr1:114716127 C\>T|missense\_variant|ENST00000369535|+|SNV|
|1|input01\_2|1|152304661|G|C|chr1|152304661|snp|+|input01|FLG|R3409G|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr1:152304661 G\>C|missense\_variant|ENST00000368799|+|SNV|
|2|input01\_3|11|115209621|G|A|chr11|115209621|snp|+|input01|CADM1|T344I|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr11:115209621 G\>A|missense\_variant|ENST00000331581|+|SNV|
|3|input01\_4|12|132140028|C|T|chr12|132140028|snp|+|input01|DDX51|--|non-protein affecting|non-protein affecting|NaN|chr12:132140028 C\>T|intron\_variant|ENST00000397333|+|SNV|
|4|input01\_5|14|24119817|G|A|chr14|24119817|snp|+|input01|DCAF11|R338H|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr14:24119817 G\>A|missense\_variant|ENST00000446197|+|SNV|
|5|input01\_6|14|59727407|G|A|chr14|59727407|snp|+|input01|RTN1|A426V|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr14:59727407 G\>A|missense\_variant|ENST00000267484|+|SNV|
|6|input01\_7|15|24675943|G|A|chr15|24675943|snp|+|input01|NPAP1|A26T|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr15:24675943 G\>A|missense\_variant|ENST00000329468|+|SNV|
|7|input01\_8|16|67616834|G|A|chr16|67616834|snp|+|input01|CTCF|E348K|oncogenic \(predicted\)|driver \(oncodriveMUT\)|NaN|chr16:67616834 G\>A|missense\_variant|ENST00000646076|+|SNV|
|8|input01\_9|16|71389851|G|A|chr16|71389851|snp|+|input01|CALB2|E268K|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr16:71389851 G\>A|missense\_variant|ENST00000302628|+|SNV|
|9|input01\_10|16|74452195|A|C|chr16|74452195|snp|+|input01|GLG1|--|non-protein affecting|non-protein affecting|NaN|chr16:74452195 A\>C|intron\_variant|ENST00000205061|+|SNV|
|10|input01\_11|19|12943751|GCAGAGGCTTAAGGAGGAGGAAGAAGACAAGAAACGCAAAGAGGAGGAGGAG|-|chr19|12943750|indel|+|input01|CALR|EQRLKEEEEDKKRKEEEE364-381X|oncogenic \(predicted\)|driver \(oncodriveMUT\)|NaN|chr19:12943751-12943751 GCAGAGGCTTAAGGAGGAGGAAGAAGACAAGAAACGCAAAGAGGAGGAGGAG\>-|frameshift\_variant|ENST00000316448|+|DEL|
|11|input01\_12|19|35673516|A|C|chr19|35673516|snp|+|input01|UPK1A|T147P|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr19:35673516 A\>C|missense\_variant|ENST00000616789|+|SNV|
|12|input01\_13|19|45319445|T|G|chr19|45319445|snp|+|input01|CKM|--|non-protein affecting|non-protein affecting|NaN|chr19:45319445 T\>G|intron\_variant|ENST00000221476|+|SNV|
|13|input01\_14|2|137450992|G|A|chr2|137450992|snp|+|input01|THSD7B|R1036Q|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr2:137450992 G\>A|missense\_variant|ENST00000272643|+|SNV|
|14|input01\_15|2|218880905|A|C|chr2|218880905|snp|+|input01|WNT10A|--|non-protein affecting|non-protein affecting|NaN|chr2:218880905 A\>C|5\_prime\_UTR\_variant|ENST00000258411|+|SNV|
|15|input01\_16|20|32434638|-|G|chr20|32434638|indel|+|input01|ASXL1|-642-643X|oncogenic \(predicted\)|driver \(oncodriveMUT\)|NaN|chr20:32434638-32434639 -\>G|frameshift\_variant|ENST00000375687|+|INS|
|16|input01\_17|21|41901750|C|T|chr21|41901750|snp|+|input01|C2CD2|--|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr21:41901750 C\>T|splice\_acceptor\_variant|ENST00000380486|+|SNV|
|17|input01\_18|21|43094667|T|G|chr21|43094667|snp|+|input01|U2AF1|Q157P|oncogenic \(predicted and annotated\)|driver \(boostDM: non-tissue-specific model\)|cgi,oncokb,clinvar:376024|chr21:43094667 T\>G|missense\_variant|ENST00000291552|+|SNV|
|18|input01\_20|3|133380804|G|A|chr3|133380804|snp|+|input01|TMEM108|D365N|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr3:133380804 G\>A|missense\_variant|ENST00000321871|+|SNV|
|19|input01\_22|7|584561|G|A|chr7|584561|snp|+|input01|PRKAR1B|T239M|non-oncogenic|passenger \(oncodriveMUT\)|NaN|chr7:584561 G\>A|missense\_variant|ENST00000406797|+|SNV|

Como criar uma tabela mais complexa em MarkDown
>https://www.tablesgenerator.com/markdown_tables
