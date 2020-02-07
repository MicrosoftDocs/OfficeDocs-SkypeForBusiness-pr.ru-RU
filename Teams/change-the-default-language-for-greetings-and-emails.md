---
title: Изменение языка по умолчанию для приветствий и электронных писем
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'В этой статье объясняется, как настроить Skype для бизнеса, чтобы использовать другой язык для приветствия голосовой почты, используемого по умолчанию в вашей организации. '
ms.openlocfilehash: 078fd14944d5384d38d870e09575980cc89e8889
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825237"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="7fd24-103">Изменение языка по умолчанию для приветствий и электронных писем</span><span class="sxs-lookup"><span data-stu-id="7fd24-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="7fd24-104">При наличии прав [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) вы можете настроить в Skype для бизнеса приветствие голосовой почты по умолчанию на другом языке.</span><span class="sxs-lookup"><span data-stu-id="7fd24-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="7fd24-105">По умолчанию в системе задано примерно следующее приветствие: "Оставьте сообщение для Александра Петрова.</span><span class="sxs-lookup"><span data-stu-id="7fd24-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="7fd24-106">Запишите сообщение после сигнала.</span><span class="sxs-lookup"><span data-stu-id="7fd24-106">After the tone, please record your message.</span></span> <span data-ttu-id="7fd24-107">По окончании записи повесьте трубку или нажмите решетку для выбора других функций".</span><span class="sxs-lookup"><span data-stu-id="7fd24-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="7fd24-108">**Сначала ознакомьтесь со следующей важной информацией:**</span><span class="sxs-lookup"><span data-stu-id="7fd24-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="7fd24-109">**Доступные языки определяются местоположением организации**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="7fd24-110">Например, если организация находится в США, вы можете задать английский или испанский в качестве языка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7fd24-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="7fd24-111">Если организация находится в Канаде, вы можете выбрать между английским или французским языком.</span><span class="sxs-lookup"><span data-stu-id="7fd24-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="7fd24-112">Список поддерживаемых языков см. в статье [Языки для сообщений и приветствий голосовой почты в Skype для бизнеса](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7fd24-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="7fd24-p103">**Изменить язык системы только для одного пользователя организации невозможно.** Язык системы изменяется сразу для всех пользователей организации.</span><span class="sxs-lookup"><span data-stu-id="7fd24-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7fd24-115">Пользователи могут изменить для себя язык приветствий в своих параметрах после входа в систему.</span><span class="sxs-lookup"><span data-stu-id="7fd24-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="7fd24-116">**Вам требуется записывать исходящие сообщения голосовой почты?**</span><span class="sxs-lookup"><span data-stu-id="7fd24-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="7fd24-117">См. статью [Проверка голосовой почты и параметров в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="7fd24-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="7fd24-118">Для Microsoft teams: пользователи могут менять параметры голосовой почты из [параметров настольного клиента Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) .</span><span class="sxs-lookup"><span data-stu-id="7fd24-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="7fd24-119">**Вы хотите изменить язык приглашения голосовой почты?**</span><span class="sxs-lookup"><span data-stu-id="7fd24-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="7fd24-120">Для Skype для бизнеса — [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) выберите новый язык в разделе **язык запросов**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="7fd24-121">Для Microsoft teams: пользователи могут менять параметры голосовой почты из [параметров настольного клиента Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) .</span><span class="sxs-lookup"><span data-stu-id="7fd24-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="7fd24-122">Изменение языка системы сразу для всех пользователей организации</span><span class="sxs-lookup"><span data-stu-id="7fd24-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="7fd24-123">Войдите в систему с помощью учетной записи [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) по адресу[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="7fd24-123">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="7fd24-124">В центре администрирования Microsoft 365 выберите " **Параметры** > **профиля организации**".</span><span class="sxs-lookup"><span data-stu-id="7fd24-124">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Снимок экрана, на котором показано, как выбрать параметры, а затем — профиль организации.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="7fd24-126">Выберите элемент **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-126">Choose **Edit**.</span></span>
    
    ![Снимок экрана: параметр "Изменить".](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="7fd24-128">Выберите язык из списка **Предпочитаемый язык** для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="7fd24-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="7fd24-129">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7fd24-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="7fd24-130">Дополнительные статьи для администраторов</span><span class="sxs-lookup"><span data-stu-id="7fd24-130">Related articles for the admin</span></span>

- [<span data-ttu-id="7fd24-131">Телефонная система и тарифные планы</span><span class="sxs-lookup"><span data-stu-id="7fd24-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="7fd24-132">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="7fd24-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="7fd24-133">Планирование телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7fd24-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="7fd24-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="7fd24-134">Related topics</span></span>

- [<span data-ttu-id="7fd24-135">Изменение языка интерфейса и часового пояса в Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7fd24-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="7fd24-136">[Выбор дополнительного языка и настройка языковых параметров в Office 2010 и более поздних версиях](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="7fd24-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="7fd24-137">Включение или переключение языка раскладки клавиатуры</span><span class="sxs-lookup"><span data-stu-id="7fd24-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
