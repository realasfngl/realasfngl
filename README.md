## Hi, im Neon

```python
from typing    import Dict, Union, Any, List
from bs4       import BeautifulSoup
from curl_cffi import requests
from colorama  import Fore

from core      import Run

class Body:
    """
    My whole body and information!
    """
    def __init__(self) -> None:
            
        self.name: str = "Neon"
        self.age: int = 17
        self.country: str = "Germany"
        
        self.topics: List[str] = ["Reverse Engineering", "Antibot Bypassing", "Web Automation", "Mobile Automation"]
        self.main_languages: List[str] = ["Python", "JS"]
        self.middle_knowledge: List[str] = ["Java", "zig"]
        self.learning: List[str] = ["Rust", "zig"]
        self.hated_languages: List[str] = ["C++", "Go"]
        
        self.interests: List[str] = ["Coding", "Playing games", "cooking"]
        
        self.social_media: Union[str, int, Any] = {
            "Discord": "neonasfngl",
            "Telegram": "@neonasfngl",
            "Whatsapp": ‪491636478284‬,
            "Github": "https://github.com/realasfngl"
        }
    
    @Run.Error
    def projects(self) -> list:
        """
        Getting my repositories
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
