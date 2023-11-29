# SnowCLI 2.0 usage
For more information, please see the [Snow CLI Guide](https://docs.snowflake.com/LIMITEDACCESS/snowcli/snowcli-guide). Since this is an alpha release,  the documentation may not reflect the latest features.
## Environment setup
### Conda install
```
conda env create -f conda_env.yml
conda activate snowcli2
```
### Conda upgrade
**TODO:** Determine if/why this is corrupting certain plugins
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
**NOTE:** Coverage wrapper is currently limited to projects with a single procedure
```
snow snowpark build
snow snowpark deploy --replace
snow snowpark deploy --replace --install-coverage-wrapper
```
### Invoke functions and procedures
```
snow snowpark execute function "hello_function('world')"
snow snowpark execute procedure "hello_procedure('world')"
snow snowpark execute procedure "test_procedure()"
```
### View coverage reports
**NOTE:** Project must be deployed with coverage wrapper, typically in lower environment, for coverage reports to be available.
```
snow snowpark coverage report "hello_procedure(name string)"
```