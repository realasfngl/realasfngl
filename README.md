## Hi, im Neon

```python
from typing    import Optional, Dict, Union, Any, List
from bs4       import BeautifulSoup
from curl_cffi import requests
from colorama  import Fore

from core      import Run
from neon      import sex


class Body:
    """
    My whole body and information!
    """
    def __init__(self, partner: Union[Dict, Any]) -> Optional[None]:
        
        self.partner: List[str, None] = []
        self.partner.extend(partner["Partner"])
        if len(partner["Partner"]) > 3:
            print(f"{Fore.RED} Not taking more than 3! {Fore.RESET}")
            exit()
            
        self.name: Optional[str] = "Neon"
        self.age: Optional[int] = 15
        self.country: Optional[str] = "Germany"
        
        self.main_languages: List[str] = ["Python", "JS"]
        self.middle_knowledge: List[str] = ["Batch", "Html", "Lua", "Java"]
        self.learning: List[Optional[str]] = ["Rust"]
        self.hated_languages: List[Optional[str]] = ["C++", "Go"]
        
        self.interests: List[Optional[str]] = ["coding for fun", "Playing games", "being racist", "cooking"]
        
        self.social_media: Union[str, int, Any] = {
            "Discord": "njk0mja",
            "Telegram": "@basedASF88",
            "Whatsapp": 385950600999,
            "Github": "https://github.com/realasfngl"
        }
    
    @Run.Error
    def projects(self) -> Optional[list]:
        """
        Getting my repositories heh
        """
        repositories: Optional[list] = []
        
        github: Optional[str] = self.social_media["Github"]
        
        repositories_req: requests.models.Response = requests.get(f"{github}?tab=repositories")
        
        repositories.extend(
            [
                f"https://github.com{a['href']}" for a in BeautifulSoup(repositories_req.text, "html.parser").find_all("a", itemprop="name codeRepository")
            ]
        )
        return repositories
    
    @Run.Error
    def r4pe(self) -> Optional[bool]:
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
