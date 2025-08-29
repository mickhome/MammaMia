name: Update Domains
on:
  schedule:
    - cron: "0 */6 * * *"  # Esegui ogni 6 ore
  workflow_dispatch:      # Permette di avviare manualmente il workflow
  push:
    branches:    
      - '**'         # matches every branch 

jobs:
  update-domains:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout repository
      uses: actions/checkout@v4
      with:
        fetch-depth: 0
        
    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.12'
        
    - name: Install dependencies
      run: |
        pip install requests
        
    - name: List files for debugging
      run: ls -la

    - name: Update domains in config.json
      run: |
        cd ${{ github.workspace }}
        python update_domains.py
