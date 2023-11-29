# SnowCLI 2.0 usage
## Environment setup
### Conda install
```
conda env create -f conda_env.yml
conda activate snowcli2
```
### Conda upgrade
**TODO:** Determine why this is corrupting certain plugins
```
conda env update --file conda_env.yml --prune
```

### Conda destroy
```
conda deactivate
conda env remove --name snowcli2
```

# Scenarios 
## Snowpark test project
### Initialize new project
```
snow snowpark init test_project
```
### Build and deploy
```
snow snowpark build
snow snowpark deploy --replace
```
### Test functions and procedures
```
snow snowpark execute function "hello_function('world')"
snow snowpark execute procedure "hello_procedure('world')"
snow snowpark execute procedure "test_procedure()"
```