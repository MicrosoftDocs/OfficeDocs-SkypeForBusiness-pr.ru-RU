---
title: Отправка пользователю по электронной почте сведений об аудиоконференциях
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Узнайте, как отправить пользователям сообщение электронной почты со сведениями о аудиоконференции в Microsoft Teams.
ms.openlocfilehash: 13c566884c5bc3e8d5de873696541c4b88fcb271
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004201"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="c3412-103">Отправка пользователю письма с данными для аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3412-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="c3412-104">Иногда Microsoft Teams может потребоваться, чтобы вы отправили им данные для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="c3412-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="c3412-105">Для этого в свойствах пользователя щелкните Отправить сведения о конференции по электронной почте. </span><span class="sxs-lookup"><span data-stu-id="c3412-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="c3412-106">При отправке этого сообщения электронной почты оно будет содержать все сведения об аудиоконференциях, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="c3412-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="c3412-107">Телефонный номер конференции или номер телефонного подключения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3412-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="c3412-108">Идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3412-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="c3412-109">Вот пример отправленного сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c3412-109">Here is an example of the email that is sent:</span></span>
  
![Пример сообщения электронной почты для телефонной работы](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c3412-111">Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="c3412-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="c3412-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3412-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c3412-114">В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c3412-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c3412-115">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c3412-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c3412-116">В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.</span><span class="sxs-lookup"><span data-stu-id="c3412-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c3412-117">Что еще необходимо знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="c3412-117">What else should you know about this email?</span></span>

- <span data-ttu-id="c3412-118">После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты:</span><span class="sxs-lookup"><span data-stu-id="c3412-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="c3412-119">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="c3412-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="c3412-120">При сбросе ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="c3412-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="c3412-121">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="c3412-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="c3412-122">При изъятии лицензии **аудиоконференций** у пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3412-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="c3412-123">При смене поставщика аудиоконференций для пользователя с Microsoft на другого поставщика или **нет**.</span><span class="sxs-lookup"><span data-stu-id="c3412-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="c3412-124">При смене поставщика услуг аудиоконференций для пользователя на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c3412-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c3412-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c3412-125">Related topics</span></span>

[<span data-ttu-id="c3412-126">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="c3412-126">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
