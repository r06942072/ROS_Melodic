### google chrome
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
google-chrome
```
### A tool for spliting terminal  
```sudo apt-get update```  
```sudo apt-get install terminator``` 

*Split terminals vertically:  
ctrl + shift + E

*Split terminals horizontally:  
ctrl + shift + O

*move btw terminal  
alt + arrow

*close window  
ctrl + D

### python project with pipenv with Python 3 on Ubuntu
```cd project folder/
pipenv --three
pipenv install pandas numpy matplotlib
pipenv install jupyter

pipenv shell
jupyter notebook

python -m ipykernel install --user --name mygreatenv --display-name "My Great Env"
```

### vim: Setting up Vim for Python development
https://www.youtube.com/watch?v=vlb3qUiS2ZY  
```
sudo apt-get update
sudo apt-get install vim

sudo apt-get install curl vim exuberant-ctags git ack-grep
pip install pep8 flake8 pyflakes isort yapf
```

### python package: import cv2
```
pip install opencv-python
```

