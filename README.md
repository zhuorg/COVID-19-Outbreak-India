# COVID-19 Outbreak India

## [Project Website](https://piyushke.github.io/COVID-19-Outbreak-India)


**Hello Everyone,my name is Piyush Keshari aka insane_banda on Github.**

**I am a CS student at GLA University,Mathura,India and I love coding <3**

**For past 3 days I have been learning about matplotlib and pandas from youtube and I tried to implement my knowledge by making a very basic python project,which analyzes data from an api hosted by the Govt of India containing the data of COVID-19 cases in different states of India.**

**My project is almost complete and is working fine in my local machine and I have hosted it to github pages as well.**

**The problem is that I wrote a python script to convert jupyter notebook to static index.html in the root folder and it works fine on my local machine.Basically my jupyter notebook takes data from the API source and analyzes it to display useful information,but GitHub pages cannot host jupyter notebooks so the script converts notebook to index.html file and saves it directly to root directory (Idea is to make index.html serve as the home page for GitHub pages) but when I made a workflow file to serve the purpose and when it executed something unexpected happened.**

**Below is My Workflow file run.yml located in .github/workflows/run.yml**

```yml
name: Update index.html

on: 
  schedule: 
    - cron:  '* * * * *'

jobs: 
  run:
    runs-on: windows-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python
      uses: actions/setup-python@v1
      with:
        python-version: '3.x'
    - name: Install dependencies
      run: |
        dir
        python -m pip install --upgrade pip
        pip install -r requirements.txt
        python update.py
        dir
```

**NOTE: I have Used dir commands to see where the index.html file is getting stored.**

![One]('one.PNG')
**Output of first dir command**
![Two]('two.PNG')
**Output of second dir command**

**Seems like my script (update.py) is working fine but instead of saving index.html to the root directory of my Github Repo it is saving it somewhere else. I need help to make changes in my code to make index.html file to be saved on my GitHub repo as it will serve as the home page for my Github Pages.**