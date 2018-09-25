---
title: Изменение языка по умолчанию для приветствий и электронных писем
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Сведения о настройке Skype для бизнеса с целью использования другого языка для записи приветствия голосовой почты по умолчанию. '
ms.openlocfilehash: b1937434fd63c16155916e349d15617bb36d9369
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016415"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="7f2db-103">Изменение языка по умолчанию для приветствий и электронных писем</span><span class="sxs-lookup"><span data-stu-id="7f2db-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="7f2db-104">При наличии прав [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) вы можете настроить в Skype для бизнеса приветствие голосовой почты по умолчанию на другом языке.</span><span class="sxs-lookup"><span data-stu-id="7f2db-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="7f2db-105">По умолчанию в системе задано примерно следующее приветствие: "Оставьте сообщение для Александра Петрова.</span><span class="sxs-lookup"><span data-stu-id="7f2db-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="7f2db-106">После сигнала запишите сообщение.</span><span class="sxs-lookup"><span data-stu-id="7f2db-106">After the tone, please record your message.</span></span> <span data-ttu-id="7f2db-107">По окончании записи повесьте трубку или нажмите решетку для перехода к дополнительным параметрам".</span><span class="sxs-lookup"><span data-stu-id="7f2db-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="7f2db-108">**Сначала ознакомьтесь со следующей важной информацией:**</span><span class="sxs-lookup"><span data-stu-id="7f2db-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="7f2db-109">**Доступные языки определяются местоположением организации**.</span><span class="sxs-lookup"><span data-stu-id="7f2db-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="7f2db-110">Например, если организация находится в США, вы можете задать английский или испанский в качестве языка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7f2db-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="7f2db-111">Если организация находится в Канаде, вы можете выбрать между английским или французским языком.</span><span class="sxs-lookup"><span data-stu-id="7f2db-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="7f2db-112">Список поддерживаемых языков см. в статье [Языки для сообщений и приветствий голосовой почты в Skype для бизнеса](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7f2db-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="7f2db-p103">**Изменить язык системы только для одного пользователя организации невозможно.** Язык системы изменяется сразу для всех пользователей организации.</span><span class="sxs-lookup"><span data-stu-id="7f2db-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f2db-115">Пользователи могут изменить для себя язык приветствий в своих параметрах после входа в систему.</span><span class="sxs-lookup"><span data-stu-id="7f2db-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="7f2db-116">**Вам требуется записывать исходящие сообщения голосовой почты?**</span><span class="sxs-lookup"><span data-stu-id="7f2db-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="7f2db-117">См. статью [Проверка голосовой почты и параметров в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="7f2db-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="7f2db-118">**Требуется изменить язык запроса голосовой почты?**</span><span class="sxs-lookup"><span data-stu-id="7f2db-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="7f2db-119">Последовательно выберите пункты [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) и выбрать новый язык в разделе **Приглашения язык**.</span><span class="sxs-lookup"><span data-stu-id="7f2db-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="7f2db-120">Изменение языка системы сразу для всех пользователей организации</span><span class="sxs-lookup"><span data-stu-id="7f2db-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="7f2db-121">Вход с помощью учетной записи [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) в[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="7f2db-121">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="7f2db-122">В центре администрирования выберите **Параметры** > **Профиль организации**.</span><span class="sxs-lookup"><span data-stu-id="7f2db-122">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="7f2db-124">Выберите элемент **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7f2db-124">Choose **Edit**.</span></span>
    
    ![Choose Edit.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="7f2db-126">Выберите язык из списка **Предпочитаемый язык** для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="7f2db-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="7f2db-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f2db-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="7f2db-128">Дополнительные статьи для администраторов</span><span class="sxs-lookup"><span data-stu-id="7f2db-128">Related articles for the admin</span></span>

- [<span data-ttu-id="7f2db-129">Что такое планы звонков в Office 365?</span><span class="sxs-lookup"><span data-stu-id="7f2db-129">What are Calling Plans in Office 365?</span></span>](what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="7f2db-130">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="7f2db-130">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="7f2db-131">Планирование Телефонной системы в Office 365 с локальной связью через ТСОП в Skype для бизнеса Server 2015 или Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f2db-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="7f2db-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f2db-132">Related topics</span></span>

- [<span data-ttu-id="7f2db-133">Изменение языка интерфейса и часового пояса в Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7f2db-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="7f2db-134">[Выбор дополнительного языка и настройка языковых параметров в Office 2010 и более поздних версиях](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="7f2db-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="7f2db-135">Включение или переключение языка раскладки клавиатуры</span><span class="sxs-lookup"><span data-stu-id="7f2db-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
