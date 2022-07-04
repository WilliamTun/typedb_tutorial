
# COVID Knowledge graph tutorial:


1. Set up TypeDB and typeDB studio: https://vaticle.com/download 


```
cd <path/to/type_db>
PATH="$(pwd):$PATH"

# you can change the listening port by going to:
<path_to_type_db/server/conf/config.yml>

# change line 19 
# eg.  address: 0.0.0.0:1729 --> localhost:1729

# start the typeDB server
typedb server
```


2. Git clone:  https://github.com/typedb-osi/typedb-bio 

```
cd <path/to/typedb-data-bio-covid>/
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

3. Manually install the Datasets
4. Run:  python migrator.py -n 4
5. Open the project (TypeDB folder)
6. click on Connect & select the listening port (eg  localhost:1729)
7. In the Database button, (right of save button), choose the database (biocovid)
8. Click on bio-covid.schema.tql. 
9. Click on schema + write button on top navigation bar
10. Create a new tql file and add in a command like:
```
match 
$virus isa virus, has virus-name "SARS"; 
$gene isa gene; 
$1 ($gene, $virus) isa gene-virus-association; 
limit 20; 
```
11. Clean data + read + infer ... and click go. 







