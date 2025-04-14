# chutes代码，有人要就发吧 - 开发调优 - LINUX DO
[chutes代码，有人要就发吧 - 开发调优 - LINUX DO](https://linux.do/t/topic/558163) 

  chutes代码，有人要就发吧 - 开发调优 - LINUX DO                                             

[跳到主要内容](#main-container)

 [![](https://cdn.ldstatic.com/original/3X/b/4/b4fa45d8b03df61f5d011e173c0adf8497028b16.png)](/) 

*   ​
*   ​

*    ![](https://cdn.linux.do/letter_avatar/niyan2025/96/5_d44a9b381edc88181525e3c8350177ca.png)
       [ 2 ](# "2 个未读通知") 

*   [话题](/latest "所有话题")
*   [我的帖子](/u/niyan2025/activity/drafts "我的未发布草稿")
*   [关于](/about "关于此网站的更多详细信息")
*   [即将到来的活动](/upcoming-events "即将到来的活动")
*   更多

外部链接

*   [Status](https://status.linux.do)
*   [Connect](https://connect.linux.do)
*   [Webmail](https://webmail.linux.do)
*   [Channel](https://t.me/linux_do_channel)
*   [Telegram](https://t.me/ja_netfilter_group)

类别

*   [开发调优](/c/develop/4 "此版块包含开发、测试、调试、部署、优化、安全等方面的内容")
*   [资源荟萃](/c/resource/14 "包括软件分享、开源仓库、视频课程、书籍等分享")
*   [文档共建](/c/wiki/42 "佬友化身翰林学士，一起来编书了。")
*   [跳蚤市场](/c/trade/10 "交易相关的版块，包含实体和虚拟物品供求、拼车等等")
*   [非我莫属](/c/job/27 "学成文武艺，货与帝王家。招聘/求职分类，只能发此类信息。")
*   [读书成诗](/c/reading/32 "跟着佬友们一起在论坛读完一本书是什么体验？")
*   [扬帆起航](/c/startup/46 "扬帆起航，目标是星辰大海！")
*   [前沿快讯](/c/news/34 "前沿快讯，不出门能知天下事。")
*   [网络记忆](/c/feeds/92 "网络是有记忆的，确信！")
*   [福利羊毛](/c/welfare/36 "正经人谁花那个钱啊～ 此版块供羊毛、抽奖等福利使用。")
*   [搞七捻三](/c/gossip/11 "闲聊吹水的板块。不得讨论政治、色情等违规内容。")
*   [运营反馈](/c/feedback/2 "有关此站点、其组织、运作方式以及如何改进的讨论。")
*   [深海幽域](/c/muted/45 "冰山下的深海。帖子不会上信息流、不会被论坛搜索。")
*   [所有类别](/categories)

标签

*   [人工智能](/tag/%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD)
*   [公告](/tag/%E5%85%AC%E5%91%8A)
*   [快问快答](/tag/%E5%BF%AB%E9%97%AE%E5%BF%AB%E7%AD%94)
*   [抽奖](/tag/%E6%8A%BD%E5%A5%96)
*   [精华神帖](/tag/%E7%B2%BE%E5%8D%8E%E7%A5%9E%E5%B8%96)
*   [所有标签](/tags)

消息

*   [收件箱](/u/niyan2025/messages)

*   [我的消息串](/chat/threads "我的消息串")

频道

*   [常规频道](/chat/c/general/2 "🈲 禁止在聊天频道里发送 打卡 等无意义信息，被举报会喜提 禁言1小时 。")

直接消息

*    [![](https://cdn.linux.do/user_avatar/linux.do/xronus/48/130867_2.png)  Anivix](/chat/c/anivix/32458 "与 Anivix 聊天") 

聊天

Default

​ ​ ​

**真诚**、**友善**、**团结**、**专业**，共建你我引以为荣之社区。[《常见问题解答》](/faq)

[chutes代码，有人要就发吧](/t/topic/558163)


====================================

[开发调优](/c/develop/4)

[人工智能](/tag/人工智能)

您已选择 **0** 个帖子。

全选

取消选择

271 浏览量 19 赞 1 链接 17 用户

 [![](https://cdn.linux.do/user_avatar/linux.do/kiki/96/46564_2.png)](/u/kiki "kiki") 

 [![](https://cdn.linux.do/user_avatar/linux.do/xcafe/96/306323_2.png)](/u/xcafe "xcafe") 

 [![](https://cdn.linux.do/user_avatar/linux.do/handsome/96/477777_2.png)](/u/handsome "handsome") 

 [![](https://cdn.linux.do/user_avatar/linux.do/jhonny/96/257337_2.png)](/u/jhonny "jhonny") 

 [![](https://cdn.linux.do/user_avatar/linux.do/baipiaodang/96/558762_2.png)](/u/baipiaodang "baipiaodang") 

阅读时间 5 分钟

​

[4月 13 日](/t/topic/558163/1 "跳到第一个帖子")

1 / 17

4月 14 日

[32 分钟 前](/t/topic/558163/17)

​

[![](https://cdn.linux.do/user_avatar/linux.do/youglin/96/492133_2.png)
](/u/YougLin)

[YougLin](/u/YougLin)

一元复始

[1 小时](/t/topic/558163?u=niyan2025 "发布日期")

不要闲得无聊动我帖子权限。。。

```


`import httpx
import json
import random
import string
import time
import sys
import asyncio
from pathlib import Path
from datetime import datetime
from typing import List, Dict, Any, Optional

def generate_username(length=8):
    """Generate a random username."""
    letters = string.ascii_lowercase + string.digits
    return ''.join(random.choice(letters) for _ in range(length))

async def register_account_async(username: str, client: httpx.AsyncClient) -> Optional[Dict[str, Any]]:
    """Register a new account with the given username asynchronously."""
    url = "https://chutes.ai/auth/start?%2Fcreate="
    
    headers = {
        'Content-Type': 'application/x-www-form-urlencoded',
        'accept': 'application/json',
        'accept-language': 'en-US,en;q=0.9',
        'origin': 'https://chutes.ai',
        'priority': 'u=1, i',
        'referer': 'https://chutes.ai/auth/start',
        'sec-ch-ua': '"Google Chrome";v="135", "Not-A.Brand";v="8", "Chromium";v="135"',
        'sec-ch-ua-mobile': '?0',
        'sec-ch-ua-platform': '"Windows"',
        'sec-fetch-dest': 'empty',
        'sec-fetch-mode': 'cors',
        'sec-fetch-site': 'same-origin',
        'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36',
        'x-sveltekit-action': 'true'
    }
    
    data = {
        'username': username,
    }
    
    try:
        response = await client.post(url, headers=headers, data=data)
        response.raise_for_status()
        return response.json()
    except httpx.HTTPStatusError as e:
        print(f"HTTP error occurred for {username}: {e}")
        return None
    except Exception as e:
        print(f"An error occurred for {username}: {e}")
        return None

def register_account(username):
    """Synchronous version of register_account for backward compatibility."""
    url = "https://chutes.ai/auth/start?%2Fcreate="
    
    headers = {
        'Content-Type': 'application/x-www-form-urlencoded',
        'accept': 'application/json',
        'accept-language': 'en-US,en;q=0.9',
        'origin': 'https://chutes.ai',
        'priority': 'u=1, i',
        'referer': 'https://chutes.ai/auth/start',
        'sec-ch-ua': '"Google Chrome";v="135", "Not-A.Brand";v="8", "Chromium";v="135"',
        'sec-ch-ua-mobile': '?0',
        'sec-ch-ua-platform': '"Windows"',
        'sec-fetch-dest': 'empty',
        'sec-fetch-mode': 'cors',
        'sec-fetch-site': 'same-origin',
        'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36',
        'x-sveltekit-action': 'true'
    }
    
    data = {
        'username': username,
    }
    
    try:
        response = httpx.post(url, headers=headers, data=data)
        response.raise_for_status()
        return response.json()
    except httpx.HTTPStatusError as e:
        print(f"HTTP error occurred: {e}")
        return None
    except Exception as e:
        print(f"An error occurred: {e}")
        return None

def extract_account_info(response_data):
    """Extract important account information from the registration response."""
    if not response_data or response_data.get("type") != "success":
        return None
    
    try:
        # Parse the data string from the response
        data_str = response_data.get("data", "")
        data = json.loads(data_str)
        
        # Based on the example response structure
        username = data[2]  # Username is at index 2
        user_id = data[3]   # User ID is at index 3
        created_at = data[5]  # Creation timestamp is at index 5
        hotkey = data[6]    # Hotkey is at index 6
        coldkey = data[7]   # Coldkey is at index 7
        api_key = data[10]['secret_key']  # API key is in a nested structure
        
        # Create a structured dictionary with the extracted information
        account_info = {
            "username": username,
            "user_id": user_id,
            "created_at": created_at,
            "hotkey": hotkey,
            "coldkey": coldkey,
            "api_key": api_key
        }
        
        return account_info
    except (json.JSONDecodeError, IndexError, KeyError, TypeError) as e:
        print(f"Error extracting account info: {e}")
        return None

def load_usernames_from_file(file_path):
    """Load usernames from a text file."""
    try:
        with open(file_path, 'r') as f:
            # Read lines and strip whitespace, filter out empty lines
            usernames = [line.strip() for line in f if line.strip()]
        
        if not usernames:
            print("No valid usernames found in the file.")
            return []
        
        print(f"Loaded {len(usernames)} usernames from {file_path}")
        return usernames
    except FileNotFoundError:
        print(f"Error: File {file_path} not found.")
        return []
    except Exception as e:
        print(f"Error loading usernames from file: {e}")
        return []

def save_account_data(accounts):
    """Save the registered account data to a JSON file."""
    output_dir = Path("registered_accounts")
    output_dir.mkdir(exist_ok=True)
    
    timestamp = datetime.now().strftime("%Y%m%d_%H%M%S")
    output_file = output_dir / f"accounts_{timestamp}.json"
    
    with open(output_file, "w") as f:
        json.dump(accounts, f, indent=2)
    
    print(f"Saved {len(accounts)} accounts to {output_file}")

async def process_single_registration(username: str, client: httpx.AsyncClient) -> Optional[Dict[str, Any]]:
    """Process a single registration asynchronously."""
    result = await register_account_async(username, client)
    
    if result and result.get("type") == "success":
        print(f"✅ Successfully registered: {username}")
        
        # Extract and display important account information
        account_info = extract_account_info(result)
        if account_info:
            print(f"\nAccount Information for {username}:")
            print(f"  Username: {account_info['username']}")
            print(f"  User ID: {account_info['user_id']}")
            print(f"  API Key: {account_info['api_key']}")
            
            account_data = {
                "username": username,
                "extracted_info": account_info,
                "full_response": result
            }
            return account_data
        else:
            print(f"⚠️ Couldn't extract account information from response for {username}")
            account_data = {
                "username": username,
                "registration_data": result
            }
            return account_data
    else:
        print(f"❌ Failed to register: {username}")
        return None

async def process_registrations_async(usernames: List[str], concurrency: int = 5, rate_limit: Optional[float] = None) -> List[Dict[str, Any]]:
    """Process registrations for a list of usernames asynchronously with controlled concurrency."""
    successful_accounts = []
    
    print(f"Starting concurrent registration with concurrency level: {concurrency}")
    
    # Create a semaphore to limit concurrent requests
    semaphore = asyncio.Semaphore(concurrency)
    
    async def limited_register(username):
        async with semaphore:
            if rate_limit:
                # Apply rate limiting if specified
                await asyncio.sleep(random.uniform(0, rate_limit))
            async with httpx.AsyncClient(timeout=30.0) as client:
                return await process_single_registration(username, client)
    
    # Create tasks for all usernames
    tasks = [limited_register(username) for username in usernames]
    
    # Process results as they complete
    for i, result_task in enumerate(asyncio.as_completed(tasks)):
        result = await result_task
        if result:
            successful_accounts.append(result)
            
    return successful_accounts

def process_registrations(usernames, delay_seconds):
    """Process registrations for a list of usernames synchronously (legacy method)."""
    successful_accounts = []
    
    for i, username in enumerate(usernames):
        print(f"Registering account {i+1}/{len(usernames)}: {username}")
        
        result = register_account(username)
        
        if result and result.get("type") == "success":
            print(f"✅ Successfully registered: {username}")
            
            # Extract and display important account information
            account_info = extract_account_info(result)
            if account_info:
                print("\nAccount Information:")
                print(f"  Username: {account_info['username']}")
                print(f"  User ID: {account_info['user_id']}")
                print(f"  Created: {account_info['created_at']}")
                print(f"  API Key: {account_info['api_key']}")
                print(f"  Coldkey: {account_info['coldkey']}")
                print(f"  Hotkey: {account_info['hotkey']}")
                
                account_data = {
                    "username": username,
                    "extracted_info": account_info,
                    "full_response": result
                }
                successful_accounts.append(account_data)
            else:
                print("⚠️ Couldn't extract account information from response")
                account_data = {
                    "username": username,
                    "registration_data": result
                }
                successful_accounts.append(account_data)
        else:
            print(f"❌ Failed to register: {username}")
        
        if i < len(usernames) - 1:
            print(f"Waiting {delay_seconds} seconds before next request...")
            time.sleep(delay_seconds)
    
    return successful_accounts

async def main_async():
    print("Chutes.ai Account Registration Tool")
    print("==================================\n")
    
    # Get registration mode
    print("Registration modes:")
    print("1. Bulk registration with random usernames")
    print("2. Register with custom usernames (manual input)")
    print("3. Register a single custom username")
    print("4. Load usernames from file")
    print("5. Concurrent registration with random usernames")
    print("6. Concurrent registration with custom usernames")
    
    while True:
        try:
            mode = int(input("\nSelect mode (1-6): "))
            if 1 <= mode <= 6:
                break
            else:
                print("Please enter a number between 1 and 6.")
        except ValueError:
            print("Please enter a valid number.")
    
    successful_accounts = []
    
    if mode == 1:
        # Bulk registration with random usernames
        num_accounts = int(input("Number of accounts to register: "))
        delay_seconds = float(input("Delay between requests (seconds): "))
        
        usernames = [generate_username() for _ in range(num_accounts)]
        successful_accounts = process_registrations(usernames, delay_seconds)
    
    elif mode == 2:
        # Register with custom usernames from manual input
        print("\nEnter usernames, one per line. Enter an empty line when finished.")
        usernames = []
        
        while True:
            username = input(f"Username {len(usernames) + 1}: ")
            if not username:
                if usernames:
                    break
                else:
                    print("Please enter at least one username.")
                    continue
            usernames.append(username)
        
        delay_seconds = float(input("Delay between requests (seconds): "))
        successful_accounts = process_registrations(usernames, delay_seconds)
    
    elif mode == 3:
        # Register a single custom username
        username = input("Enter username: ")
        
        print(f"Registering account: {username}")
        result = register_account(username)
        
        if result and result.get("type") == "success":
            print(f"✅ Successfully registered: {username}")
            
            # Extract and display important account information
            account_info = extract_account_info(result)
            if account_info:
                print("\nAccount Information:")
                print(f"  Username: {account_info['username']}")
                print(f"  User ID: {account_info['user_id']}")
                print(f"  Created: {account_info['created_at']}")
                print(f"  API Key: {account_info['api_key']}")
                print(f"  Coldkey: {account_info['coldkey']}")
                print(f"  Hotkey: {account_info['hotkey']}")
                
                account_data = {
                    "username": username,
                    "extracted_info": account_info,
                    "full_response": result
                }
                successful_accounts.append(account_data)
            else:
                print("⚠️ Couldn't extract account information from response")
                account_data = {
                    "username": username,
                    "registration_data": result
                }
                successful_accounts.append(account_data)
        else:
            print(f"❌ Failed to register: {username}")
    
    elif mode == 4:
        # Load usernames from file
        file_path = input("Enter path to file containing usernames (one per line): ")
        usernames = load_usernames_from_file(file_path)
        
        if usernames:
            delay_seconds = float(input("Delay between requests (seconds): "))
            successful_accounts = process_registrations(usernames, delay_seconds)
    
    elif mode == 5:
        # Concurrent registration with random usernames
        num_accounts = int(input("Number of accounts to register: "))
        concurrency = int(input("Number of concurrent requests (recommended 5-10): "))
        rate_limit = float(input("Random delay between requests (seconds, 0 for no delay): ") or 0)
        
        if rate_limit <= 0:
            rate_limit = None
            
        usernames = [generate_username() for _ in range(num_accounts)]
        successful_accounts = await process_registrations_async(usernames, concurrency, rate_limit)
    
    elif mode == 6:
        # Concurrent registration with custom usernames
        source = input("Source (1: Manual input, 2: File): ")
        
        usernames = []
        if source == "1":
            print("\nEnter usernames, one per line. Enter an empty line when finished.")
            while True:
                username = input(f"Username {len(usernames) + 1}: ")
                if not username:
                    if usernames:
                        break
                    else:
                        print("Please enter at least one username.")
                        continue
                usernames.append(username)
        else:
            file_path = input("Enter path to file containing usernames (one per line): ")
            usernames = load_usernames_from_file(file_path)
            
        if usernames:
            concurrency = int(input("Number of concurrent requests (recommended 5-10): "))
            rate_limit = float(input("Random delay between requests (seconds, 0 for no delay): ") or 0)
            
            if rate_limit <= 0:
                rate_limit = None
                
            successful_accounts = await process_registrations_async(usernames, concurrency, rate_limit)
    
    if successful_accounts:
        save_account_data(successful_accounts)
    
    print(f"\nRegistration complete. Successfully registered {len(successful_accounts)} account(s).")

def main():
    asyncio.run(main_async())

if __name__ == "__main__":
    main()` 
```

顺便放个不知道多少个账号  
[accounts\_20250409\_202612.txt](/uploads/short-url/koRNC1plHUbodl6GIqbQikxBRot.txt)

(1.2 MB)

  

1 个回复

![](https://cdn.linux.do/images/emoji/twemoji/heart.png?v=14)

heart

![](https://cdn.linux.do/images/emoji/twemoji/+1.png?v=14)

+1

![](https://cdn.linux.do/images/emoji/twemoji/laughing.png?v=14)

laughing

16

​ ​ 回复

*   [chutes，全天底下最草台班子](https://linux.do/t/topic/556262)
    

271 浏览量 19 赞 1 链接 17 用户

 [![](https://cdn.linux.do/user_avatar/linux.do/kiki/96/46564_2.png)](/u/kiki "kiki") 

 [![](https://cdn.linux.do/user_avatar/linux.do/xcafe/96/306323_2.png)](/u/xcafe "xcafe") 

 [![](https://cdn.linux.do/user_avatar/linux.do/handsome/96/477777_2.png)](/u/handsome "handsome") 

 [![](https://cdn.linux.do/user_avatar/linux.do/jhonny/96/257337_2.png)](/u/jhonny "jhonny") 

 [![](https://cdn.linux.do/user_avatar/linux.do/baipiaodang/96/558762_2.png)](/u/baipiaodang "baipiaodang") 

阅读时间 5 分钟

[![](https://cdn.linux.do/user_avatar/linux.do/baipiaodang/96/558762_2.png)
](/u/baipiaodang)

[baipiaodang](/u/baipiaodang)

 ![](https://cdn.linux.do/images/emoji/twemoji/speech_balloon.png?v=14) 

[1 小时](/t/topic/558163/2?u=niyan2025 "发布日期")

还在发力

  

1

​ ​ 回复

[![](https://cdn.linux.do/letter_avatar/unboxed/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/unboxed)

[C C](/u/unboxed)

[unboxed](/u/unboxed)

[1 小时](/t/topic/558163/3?u=niyan2025 "发布日期")

大佬太强了

  

1

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/kiki/96/46564_2.png)
](/u/kiki)

[kiki](/u/kiki)

种子用户

[1 小时](/t/topic/558163/4?u=niyan2025 "发布日期")

杀杀杀杀杀~一个都别想活~

  

1

​ ​ 回复

[![](https://cdn.linux.do/letter_avatar/miaoxing/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/miaoxing)

[喵星人](/u/miaoxing)

[miaoxing](/u/miaoxing)

[1 小时](/t/topic/558163/5?u=niyan2025 "发布日期")

佬这是受什么刺激了。

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/jhonny/96/257337_2.png)
](/u/jhonny)

[jhonny](/u/jhonny)

一元复始 ![](https://cdn.linux.do/images/emoji/twemoji/thinking.png?v=14) 

[1 小时](/t/topic/558163/6?u=niyan2025 "发布日期")

佬太强啦

  

​ ​ 回复

[![](https://cdn.linux.do/letter_avatar/zxc12/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/zxc12)

[清漪](/u/zxc12)

[zxc12](/u/zxc12)活跃用户

[1 小时](/t/topic/558163/7?u=niyan2025 "发布日期")

虽然看不懂但不妨碍我点赞 ![](https://cdn.linux.do/images/emoji/twemoji/+1.png?v=14)

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/namei_zz/96/564157_2.png)
](/u/NaMei_ZZ)

[当前版本奈德丽肆虐上路](/u/NaMei_ZZ)

[NaMei\_ZZ](/u/NaMei_ZZ)圆圆满满 ![](https://cdn.ldstatic.com/original/3X/5/3/535b871b10c649510280825c98e80ee1122613ec.png?v=14) 

[1 小时](/t/topic/558163/8?u=niyan2025 "发布日期")

冲冲冲冲冲冲

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/delicious/96/574954_2.png)
](/u/delicious)

[delicious](/u/delicious)

[1 小时](/t/topic/558163/9?u=niyan2025 "发布日期")

大佬牛逼

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/ab3r/96/369668_2.png)
](/u/aB3R)

[aBER](/u/aB3R)

[aB3R](/u/aB3R)Regular ![](https://cdn.linux.do/images/emoji/twemoji/japanese_ogre.png?v=14) 

[1 小时](/t/topic/558163/10?u=niyan2025 "发布日期")

有求必应, 彻底疯狂 ![](https://cdn.ldstatic.com/original/3X/8/f/8f4cd075b79901fe3bba0313caa6a80bee2dc937.png?v=14)

  

​ ​ 回复

[![](https://cdn.linux.do/letter_avatar/deloz/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/Deloz)

[Deleted](/u/Deloz)

[Deloz](/u/Deloz)

[1 小时](/t/topic/558163/11?u=niyan2025 "发布日期")

还能这样啊

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/handsome/96/477777_2.png)
](/u/handsome)

[大帅哥](/u/handsome)

[handsome](/u/handsome)种子用户 ![](https://cdn.linux.do/images/emoji/twemoji/rage.png?v=14) 

[1 小时](/t/topic/558163/12?u=niyan2025 "发布日期")

太强了，大佬！

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/acloudee/96/546428_2.png)
](/u/acloudee)

[qiuba](/u/acloudee)

[acloudee](/u/acloudee)

[1 小时](/t/topic/558163/13?u=niyan2025 "发布日期")

佬友太厉害了

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/wyntalgeer/96/560471_2.png)
](/u/wyntalgeer)

[wyntalgeer](/u/wyntalgeer)

[1 小时](/t/topic/558163/14?u=niyan2025 "发布日期")

停不下来，根本停不下来

  

​ ​ 回复

[![](https://cdn.linux.do/letter_avatar/powerpanda/96/5_d44a9b381edc88181525e3c8350177ca.png)
](/u/powerpanda)

[powerpanda](/u/powerpanda)

[41 分钟](/t/topic/558163/15?u=niyan2025 "发布日期")

![](https://cdn.linux.do/user_avatar/linux.do/youglin/48/492133_2.png)
 YougLin:

> `https://chutes.ai`

403???

  

​ ​ 回复

[![](https://cdn.linux.do/user_avatar/linux.do/xcafe/96/306323_2.png)
](/u/xcafe)

[xcafe](/u/xcafe)

大预言家

[39 分钟](/t/topic/558163/16?u=niyan2025 "发布日期")

![](https://cdn.ldstatic.com/original/4X/b/a/1/ba139d1f448b22527b8de154d44dece4de16b680.gif)

  
脑子里想到这个了

  

​ ​ 回复

上次访问

[![](https://cdn.linux.do/user_avatar/linux.do/jamrin/96/556227_2.png)
](/u/JamRin)

[表面是风驰电掣的职场新星，实则在手偶吐槽与爆肝日常中寻找甜味的追光者宫森葵](/u/JamRin)

[JamRin](/u/JamRin)活跃用户 ![](https://cdn.ldstatic.com/original/3X/1/6/16baef70ba80d438e4bb1907ec0c354d680e09df.png?v=14) 

[32 分钟](/t/topic/558163/17?u=niyan2025 "发布日期")

佬友太强了！！！

  

​ ​ 回复

### 此话题将在最后一个回复的1 个月后关闭。

分享 加入书签 举报

回复

已取消置顶

​

此话题已对您取消置顶；它将以常规顺序显示

常规 您会在别人 @ 您或回复您时收到通知。

  

*   推荐
*   相关

### 新话题和未读话题

话题列表，带有按钮的列标题可以排序。
| 话题 | 回复 | 浏览量 | 活动 |
| --- | --- | --- | --- |
| [分享一个我的翻译提示词，配合沉浸式翻译爽的飞起！(03-29提示词更新,专有名词兼容)](/t/topic/515672/73)

 [171](/t/topic/515672/73 "您在此话题中有 171 个未读帖子")

[开发调优](/c/develop/4)

[人工智能](/tag/人工智能)





 | [240](/t/topic/515672/1) | 5.9k | [3 天](/t/topic/515672/243) |
| [\[Cursor\] 最稳定的自动更新禁用方案](/t/topic/297886/103)

 [43](/t/topic/297886/103 "您在此话题中有 43 个未读帖子")

[开发调优](/c/develop/4)

[配置优化](/tag/配置优化)





 | [140](/t/topic/297886/1) | 9.8k | [6 天](/t/topic/297886/145) |
| [对于Youtube或者B站上没有字幕的视频如何在线总结内容？](/t/topic/535349/24)

 [1](/t/topic/535349/24 "您在此话题中有 1 个未读帖子")

[开发调优](/c/develop/4)

[快问快答](/tag/快问快答)

,[人工智能](/tag/人工智能)





 | [22](/t/topic/535349/1) | 510 | [8 天](/t/topic/535349/24) |
| [Chrome冷启动CPU占用高且某一进程无响应](/t/topic/479020/29)

 [7](/t/topic/479020/29 "您在此话题中有 7 个未读帖子")

[开发调优](/c/develop/4)

[快问快答](/tag/快问快答)

,[配置优化](/tag/配置优化)





 | [34](/t/topic/479020/1) | 255 | [3月 7 日](/t/topic/479020/35) |
| [【已发布到 Github Marketplace】Github 快速搭建博客/文档网站：保持专注于内容创作](/t/topic/353423/31)

 [7](/t/topic/353423/31 "您在此话题中有 7 个未读帖子")

[开发调优](/c/develop/4)

[配置优化](/tag/配置优化)

,[博客](/tag/博客)





 | [34](/t/topic/353423/1) | 774 | [1月 27 日](/t/topic/353423/37) |

### 有 [32 个未读](/unread)

话题 和 [130 个新](/new)

话题， 或浏览[开发调优](/c/develop/4)

中的其他话题

Invalid date Invalid date

Settings
========

🏷️ UTags - Add usertags to links

Other Extensions
----------------

[🔗 Links Helper](https://greasyfork.org/en/scripts/464541-links-helper)

[V2EX.REP - 专注提升 V2EX 主题回复浏览体验](https://greasyfork.org/en/scripts/466589-v2ex-rep-%E4%B8%93%E6%B3%A8%E6%8F%90%E5%8D%87-v2ex-%E4%B8%BB%E9%A2%98%E5%9B%9E%E5%A4%8D%E6%B5%8F%E8%A7%88%E4%BD%93%E9%AA%8C)

[v2ex.min - V2EX Minimalist (极简风格)](https://greasyfork.org/en/scripts/463552-v2ex-min-v2ex-%E6%9E%81%E7%AE%80%E9%A3%8E%E6%A0%BC)

[Replace Ugly Avatars](https://greasyfork.org/en/scripts/472616-replace-ugly-avatars)

↑↓⇔⇧⇩