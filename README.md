# Senior Project : Privacy Preserving Search Engine

ABSTRACT : The objective is to create a decentralized, private search engine hosted on a server, to protect the user’s privacy and security, whilst also having the main benefits of a search engine and proving that privacy is enlisted. Used was the private search engine, SEARX.

## Implementation
Implementation will also be covered in the Presentation.

1. If you are on a Windows Computer, you can do two things. Either a) host your own Ubuntu Server by downloading Ubuntu from the Microsoft store or b) Dowload Virtualbox or the VM system oof your choice and create a Linux VM.
2. Open up the elevated terminal or powershell, you must be in root terminal in order to run this successfully.
3. Here are the commands (Linux terminal) you will be using, keep in mind that these are updated for Python 3. On many websites, the commands listed only work for Python 2.7 which is not in service any more.
   * sudo apt update
   * sudo apt-get upgrade
   *  sudo apt-get install git build-essential libxslt-dev python-dev python3-virtualenv uwsgi uwsgi-plugin-python3 python-babel zlib1g-dev libffi-dev libssl-dev shellcheck
      * Installs all packages needed for uWSGI  
   *  sudo -i 
      * If you are not already elevated, this command will do so
   *  cd /usr/local/
   *  sudo git clone https://github.com/jagra27/searx.git
      * If you are experiencing any issues with checking out of the repo, delete the folder and try again. If issues persist, clone from here https://github.com/searx/searx.git
   *  sudo useradd searx -d /usr/local/searx 
      *  Creates a user
   *  sudo chown searx:searx -R /usr/local/searx
   *  sudo apt-get install python3-pip
   *  sudo -H sed -i -e "s/ultrasecretkey/$(openssl rand -hex 16)/g" "searx/searx/settings.yml"
   * sudo nano searx/searx/settings.yml  
     * You can see your ultrasecretkey, then save and exit
     * This is also where you can see your address, logging, port number, etc.
   *   sudo virtualenv -p python3 searx-ve
   *   . ./searx-ve/bin/activate
   *   cd searx
   *   pip3 install -r requirements.txt
   *   python3 searx/webapp.py
4. Once the last command successfully runs, you should be able to acess your private, local instance of Searx using your favorite Internet browser.

## Challenges
Running a private,local instance of SearX is remarkably difficult if you have a Macbook Apple M1 Chip and do not have the resources to download a Linux VM or Server. There are very few resources online available to help.
Having a full understanding of how SearX is able to use other engines whilst still maintaining privacy was difficult, however, with the help of readings and videos, I was able to do so.

### References

David Sánchez, Jordi Castellà-Roca, Alexandre Viejo,Knowledge-based scheme to create privacy-preserving but semantically-related queries for web search engines,
Information Sciences, Volume 218, 2013, Pages 17-30, ISSN 0020-0255,https://doi.org/10.1016/j.ins.2012.06.025.(https://www.sciencedirect.com/science/article/pii/S0020025512004410 )

Installation¶. Installation - Searx Documentation (Searx-1.0.0.tex). (n.d.). Retrieved April 2, 2022, from https://searx.github.io/searx/admin/installation.html 

Selles, T. S. (n.d.). Searx: Moving away from duckduckgo. Retrieved April 5, 2022, from https://sagrista.info/blog/2021/searx-or-duckduckgo/ 

Taylor, S. (2022, March 11). 10 best private search engines for 2022 (no logging). RestorePrivacy. Retrieved March 22, 2022, from https://restoreprivacy.com/private-search-engine/ 
