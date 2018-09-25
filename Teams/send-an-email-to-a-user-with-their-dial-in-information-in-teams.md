---
title: Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения об отправке пользователям сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams.
ms.openlocfilehash: 9ebd650e487b4ef3108d50ecce31eea0a936b176
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012323"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="bd461-103">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd461-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="bd461-104">В некоторых случаях Microsoft группами пользователей может потребоваться отправить свои данные для конференции аудио.</span><span class="sxs-lookup"><span data-stu-id="bd461-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="bd461-105">Это можно сделать, нажав кнопку **Отправить сведения о конференции по электронной почте** в разделе свойства для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd461-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="bd461-106">При отправке это сообщение, он будет содержать все сведения аудиоконференций, включая:</span><span class="sxs-lookup"><span data-stu-id="bd461-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="bd461-107">телефонный номер конференции или номер телефонного подключения для пользователя;</span><span class="sxs-lookup"><span data-stu-id="bd461-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="bd461-108">идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd461-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="bd461-109">Далее приведен пример отправляемого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="bd461-109">Here is an example of the email that is sent:</span></span>
  
![Сообщение о конференц-связи с телефонным подключением](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="bd461-111">Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="bd461-111">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="bd461-112">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="bd461-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bd461-113">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="bd461-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bd461-114">В области **Аудиоконференции** щелкните на элементе **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="bd461-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="bd461-115">Что еще нужно знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="bd461-115">What else should you know about this email?</span></span>

- <span data-ttu-id="bd461-116">Когда пользователям в вашей организации разрешены аудиоконференции, им направляется несколько сообщений электронной почты в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="bd461-116">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="bd461-117">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="bd461-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="bd461-118">Сброс ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="bd461-118">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="bd461-119">Сброс идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="bd461-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="bd461-120">При изъятии лицензии **аудиоконференций** у пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd461-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="bd461-121">Изменение поставщика услуг аудиоконференций с Майкрософт на другого поставщика или на значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="bd461-121">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="bd461-122">Изменение поставщика услуг аудиоконференций на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bd461-122">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="bd461-123">По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd461-123">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell.</span></span> <span data-ttu-id="bd461-124">В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="bd461-124">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bd461-125">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bd461-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bd461-p103">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="bd461-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd461-129">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="bd461-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bd461-130">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd461-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bd461-131">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="bd461-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="bd461-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bd461-132">Related topics</span></span>

[<span data-ttu-id="bd461-133">Оцените или приобретите аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="bd461-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
