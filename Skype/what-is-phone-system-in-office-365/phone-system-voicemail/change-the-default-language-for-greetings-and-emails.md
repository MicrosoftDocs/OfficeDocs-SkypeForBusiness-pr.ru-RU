---
title: "Изменить язык по умолчанию для приветствия и по электронной почте"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Phone System
description: 'Learn how to setup Skype for Busineses to use another language for your organization''s default voicemail greeting. '
ms.openlocfilehash: cfbdcfec46a79c6fcef2aff970a05837460f6e72
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="ec9a7-103">Изменить язык по умолчанию для приветствия и по электронной почте</span><span class="sxs-lookup"><span data-stu-id="ec9a7-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="ec9a7-104">Если вы являетесь [глобального администратора Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), можно настроить Скайп для бизнеса для воспроизведения его голосовой почты по умолчанию, приветствия на другом языке.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="ec9a7-105">Приветствие системы по умолчанию — это что-то вроде «можно оставить сообщение для John Smith.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="ec9a7-106">После звонка Запишите сообщение.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-106">After the tone, please record your message.</span></span> <span data-ttu-id="ec9a7-107">По завершении записи Разорвите или нажмите клавишу фунт Дополнительные параметры.»</span><span class="sxs-lookup"><span data-stu-id="ec9a7-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="ec9a7-108">**Сначала ознакомьтесь со следующей важной информацией:**</span><span class="sxs-lookup"><span data-stu-id="ec9a7-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="ec9a7-109">**Языки, которые можно использовать в определяются местонахождение вашей организации**.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="ec9a7-110">Например если ваша организация находится в США, можно задать язык по умолчанию английский и испанский.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="ec9a7-111">Если ваша организация находится в Канада, вы можете выбрать одну английскую и французскую версию.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="ec9a7-112">Список поддерживаемых языков в разделе [языки для приветствия голосовой почты и сообщения от Скайп для бизнеса](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ec9a7-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="ec9a7-p103">**Изменить язык системы только для одного пользователя организации невозможно.** Язык системы изменяется сразу для всех пользователей организации.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec9a7-115">Пользователи могут изменить для себя язык приветствий с помощью своих параметров после входа.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="ec9a7-116">**Хотите ли Вы записать исходящие сообщения голосовой почты?**</span><span class="sxs-lookup"><span data-stu-id="ec9a7-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="ec9a7-117">В разделе [Проверка Скайп Business голосовой почты и параметров](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="ec9a7-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="ec9a7-118">Изменение языка системы сразу для всех пользователей организации</span><span class="sxs-lookup"><span data-stu-id="ec9a7-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="ec9a7-119">Вход с помощью учетной записи [глобального администратора Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) в[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="ec9a7-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="ec9a7-120">В центре администрирования выберите **Параметры** > **Профиль организации**.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="ec9a7-122">Выберите элемент **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="ec9a7-124">Выберите язык из списка **Предпочитаемый язык** для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="ec9a7-125">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ec9a7-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="ec9a7-126">Дополнительные статьи для администраторов</span><span class="sxs-lookup"><span data-stu-id="ec9a7-126">Related articles for the admin</span></span>

- [<span data-ttu-id="ec9a7-127">Что такое планы звонков в Office 365?</span><span class="sxs-lookup"><span data-stu-id="ec9a7-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="ec9a7-128">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="ec9a7-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="ec9a7-129">Телефонная система планов в Office 365 с использованием локальных подключений к ТСОП в Skype для бизнеса Server 2015 или Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec9a7-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="ec9a7-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec9a7-130">Related topics</span></span>

- [<span data-ttu-id="ec9a7-131">Изменение языка интерфейса и часового пояса в Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ec9a7-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="ec9a7-132">[Добавление языка или задать предпочтительный язык в Office 2010 и более поздних версий](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="ec9a7-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="ec9a7-133">Включение или переключение языка раскладки клавиатуры</span><span class="sxs-lookup"><span data-stu-id="ec9a7-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

