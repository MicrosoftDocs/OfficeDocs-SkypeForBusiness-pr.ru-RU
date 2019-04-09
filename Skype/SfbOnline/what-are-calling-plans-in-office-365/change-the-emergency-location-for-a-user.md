---
title: Назначение и изменение расположения экстренного реагирования для пользователя
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Узнайте, как изменить местоположение для реагирования экстренных служб для пользователей. С помощью безлимитного числа местоположений, можно изменить местоположения для реагирования экстренных служб, по мере того как сотрудники двигаются между этажами и зданиями. '
ms.openlocfilehash: 79ba52d65dc87b36397d4d0a8df121ac1fec8262
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "31516945"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a><span data-ttu-id="e1747-104">Назначение и изменение расположения экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="e1747-104">Assign or change the emergency location for a user</span></span>

<span data-ttu-id="e1747-105">Каждый номер телефона active должен быть связанного экстренных адрес при назначение номер телефона для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1747-105">Each active phone number must have an associated emergency address when you assign the phone number to a user.</span></span> <span data-ttu-id="e1747-106">(Свяжите адрес при получении номер телефона в Office 365 или при перемещении номера телефона.) При связывании номер экстренного адрес также можно добавить экстренных расположение для предоставления более точное расположения в физическое расположение.</span><span class="sxs-lookup"><span data-stu-id="e1747-106">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="e1747-107">Местоположение для экстренного реагирования может быть этажом, крылом или номером офиса, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="e1747-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="e1747-108">У вас есть безлимитное число местоположений для заданного адреса для экстренного реагирования, и вы можетеизменить местоположение для реагирования экстренных служб, если пользователь перемещается в другой офис или здание — например, при перемещении c 34 на 35 этаж.</span><span class="sxs-lookup"><span data-stu-id="e1747-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="e1747-109">Чтобы узнать о том, как получить тарифные планы Office 365 и их стоимость, см. раздел [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e1747-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-the-emergency-location"></a><span data-ttu-id="e1747-110">Назначение или изменение экстренных расположения</span><span class="sxs-lookup"><span data-stu-id="e1747-110">Assign or change the emergency location</span></span>

1. <span data-ttu-id="e1747-111">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="e1747-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e1747-112">Перейдите в **Центр администрирования группами Майкрософт** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="e1747-112">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="e1747-113">В левой панели навигации выберите пункты **голосовой связи** > **пользователей голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="e1747-113">In the left navigation go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e1747-114">Позволяет параметр **голосовой связи** в левой области навигации в Скайп по центру администрирования бизнеса необходимо купить по крайней мере один **E5 корпоративной лицензии**, дополнительная лицензия на одной **Телефонной системой** или дополнительная лицензия на один **Аудио конференц-связи** .</span><span class="sxs-lookup"><span data-stu-id="e1747-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="e1747-115">На странице **Пользователи голосовой связи** найдите и выберите пользователя, для которого необходимо изменить адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="e1747-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="e1747-116">На панели действий нажмите **Местоположение для реагирования экстренных служб**, затем **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e1747-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="e1747-117">На странице **Назначить номер** выберите **Изменить местоположение**.</span><span class="sxs-lookup"><span data-stu-id="e1747-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="e1747-118">В разделе **Изменить экстренных адрес для**введите название города, в поле и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="e1747-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>

8. <span data-ttu-id="e1747-119">Выберите из раскрывающегося списка **поиска в одном месте** , введите сокращенное имя для расположения (например, введите **floor**) и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="e1747-119">Select **Search by location** from the drop-down list, enter a partial name for the location (for example, enter **floor**), and then click **Search**.</span></span> 
    
8. <span data-ttu-id="e1747-120">Выберите экстренных расположения в списке и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e1747-120">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="e1747-121">Если вы хотите добавить новые экстренные расположение, которое будет отображаться в списке, содержатся в разделе [Добавление, изменение или удаление экстренных расположение для вашей организации](add-change-or-remove-an-emergency-location-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e1747-121">If you want to add a new emergency location that will appear on the list, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e1747-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e1747-122">Related topics</span></span>

[<span data-ttu-id="e1747-123">Назначение действия в чрезвычайных ситуациях расположений с помощью powershell</span><span class="sxs-lookup"><span data-stu-id="e1747-123">Assign an emergency response locations via powershell</span></span>](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[<span data-ttu-id="e1747-124">Добавление или удаление адреса для экстренного реагирования для вашей организации</span><span class="sxs-lookup"><span data-stu-id="e1747-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="e1747-125">Добавление, изменение и удаление расположения экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="e1747-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="e1747-126">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="e1747-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="e1747-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="e1747-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="e1747-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="e1747-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="e1747-129">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e1747-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
