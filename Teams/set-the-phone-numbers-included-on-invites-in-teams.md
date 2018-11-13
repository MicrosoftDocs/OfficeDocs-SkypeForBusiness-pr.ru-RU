---
title: Установка телефона, номера, находящимся на приглашает в группами Майкрософт
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Получите инструкции по созданию номер телефона по умолчанию для абонентов, чтобы присоединиться к собранию группами Майкрософт. '
ms.openlocfilehash: 859bf6f4a99f95c67123385c99061b1546eaa60c
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296273"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="05f36-103">Настройка телефонных номеров, включаемых в приглашения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05f36-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="05f36-104">Функция аудиоконференций в Office 365 позволяет пользователям вашей организации создавать собрания Microsoft Teams для подключения к ним пользователей по телефону.</span><span class="sxs-lookup"><span data-stu-id="05f36-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="05f36-105">В Office 365 есть возможность использования моста аудиоконференций Майкрософт или моста аудиоконференций сторонних разработчиков, размещенного у утвержденного поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="05f36-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="05f36-p102">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="05f36-p102">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05f36-108">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="05f36-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="05f36-109">Задание или изменение телефонного номера аудиоконференций по умолчанию для организатора собрания или пользователя</span><span class="sxs-lookup"><span data-stu-id="05f36-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="05f36-111">Использование групп Майкрософт и Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="05f36-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="05f36-112">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="05f36-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Показывает, Выбор пользователей в группы Microsoft и Скайп по центру администрирования Business](media/teamsselectusers.png)

2. <span data-ttu-id="05f36-114">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="05f36-114">At the top of the page, click **Edit**.</span></span>

    ![Нажмите кнопку Изменить в Microsoft групп и Скайп по центру администрирования Business](media/teamsedituser.png)

3. <span data-ttu-id="05f36-116">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="05f36-116">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Нажмите кнопку Изменить рядом с пунктом аудиоконференции](media/teamseditaudioconf.png)

4. <span data-ttu-id="05f36-118">Использование полей **бесплатный номер** или **бесплатный номер** для ввода цифр для пользователя.</span><span class="sxs-lookup"><span data-stu-id="05f36-118">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="05f36-119">При изменении параметров аудиоконференций пользователя повторяющиеся и будущих собраний группами Майкрософт должен быть обновлено и отправлены участникам.</span><span class="sxs-lookup"><span data-stu-id="05f36-119">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="05f36-120">Хотите использовать Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="05f36-120">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="05f36-p103">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="05f36-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="05f36-124">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="05f36-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="05f36-125">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05f36-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="05f36-126">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="05f36-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="05f36-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="05f36-127">Related topics</span></span>

[<span data-ttu-id="05f36-128">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="05f36-128">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
