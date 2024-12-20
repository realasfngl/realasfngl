## Hi, im Neon

```python
from colorama import Fore
from curl_cffi import requests
from bs4 import BeautifulSoup
from neon import sex

class body:
    """
    My whole body and information!
    """
    def __init__(self, partner: dict) -> None:
        
        self.partner: list = []
        self.partner.extend(partner["Partner"])
        if len(partner["Partner"]) > 3:
            print(f"{Fore.RED} Not taking more than 3! {Fore.RESET}")
            exit()
            
        self.name: str = "Neon"
        self.age: int = 15
        self.country: str = "Germany"
        
        self.main_language: str = "Python"
        self.middle_knowledge: list = ["Batch", "Html", "Lua", "Js", "Java"]
        self.learning: list = ["Rust"]
        self.hated_languages: list = ["C++", "Go"]
        
        self.interests: list = ["coding for fun", "Playing games", "being racist", "cooking"]
        
        self.social_media: dict = {
            "Discord": "njk0mja",
            "Telegram": "@basedASF88",
            "Whatsapp": "+385 950600999",
            "Github": "https://github.com/NeonASF"
        }
        
    def projects(self) -> list:
        """
        Getting my repositories heh
        """
        repositories: list = []
        
        github: str = self.social_media["Github"]
        
        repositories_req: requests.models.Response = requests.get(f"{github}?tab=repositories")
        
        repositories.extend(
            [
                f"https://github.com{a['href']}" for a in BeautifulSoup(repositories_req.text, "html.parser").find_all("a", itemprop="name codeRepository")
            ]
        )
        return repositories
    
    def r4pe(self) -> bool:
        """
        R4ping!
        """
        fuck: sex.r4pe.action = sex.r4pe(partners=self.partner)
        fuck.strength(10)
        fuck.fuck_for(10)
        cum: str = fuck.cum_after(30)
        if cum != None:
            return True
        else:
            return False
```
