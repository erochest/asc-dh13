Downloaded by calling

> curl -O http://asc.jebbo.co.uk/a/a.xml
> curl -O http://lexicon.ff.cuni.cz/txt/oe_bosworthtoller.txt
> curl -O http://lexicon.ff.cuni.cz/xml/oe_bosworthtoller/oebt_abbreviations.xml

The TEI P4 DTD was downloaded using this script:

```bash
URL=http://www.tei-c.org/release/xml/teip4/schema/dtd/
for rsc in $(curl $URL | grep '^<li>' | sed 's/.*"\([^"]*\)".*/\1/'); do
  echo $rsc
  curl -O $URL/$rsc
done
```

