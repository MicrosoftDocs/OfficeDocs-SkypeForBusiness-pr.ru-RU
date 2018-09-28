---
title: Изменение местоположения для реагирования экстренных служб для пользователя
ms.author: tonysmit
author: tonysmit
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
ms.openlocfilehash: 7ebec7ca6a2180702eec9e24b3165eb501d4a097
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347114"
---
# <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="72624-104">Изменение местоположения для экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="72624-104">Change the emergency location for a user</span></span>

<span data-ttu-id="72624-105">Каждый активный номер телефона должен иметь адреса для экстренного реагирования (при получении номера телефона в Office 365 или при переключении номера телефона) при назначении номера телефона для пользователя.</span><span class="sxs-lookup"><span data-stu-id="72624-105">Each active phone number must have an emergency address (associated when you get a phone number in Office 365 or when you transfer a phone number) when the phone number is assigned to the user.</span></span> <span data-ttu-id="72624-106">При ассоциировании номера адреса для экстренного реагирования также можно добавить местоположение для реагирования экстренных служб для предоставления более точного физического местоположения.</span><span class="sxs-lookup"><span data-stu-id="72624-106">When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="72624-107">Местоположение для экстренного реагирования может быть этажом, крылом или номером офиса, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="72624-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="72624-108">У вас есть безлимитное число местоположений для заданного адреса для экстренного реагирования, и вы можетеизменить местоположение для реагирования экстренных служб, если пользователь перемещается в другой офис или здание — например, при перемещении c 34 на 35 этаж.</span><span class="sxs-lookup"><span data-stu-id="72624-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="72624-109">Чтобы узнать о том, как получить тарифные планы Office 365 и их стоимость, см. раздел [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="72624-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-location-for-a-user"></a><span data-ttu-id="72624-110">Изменение местоположения для реагирования экстренных служб для пользователя</span><span class="sxs-lookup"><span data-stu-id="72624-110">Change the emergency location for a user</span></span>

1. <span data-ttu-id="72624-111">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="72624-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="72624-112">Последовательно выберите пункты **группами Майкрософт и Скайп по центру администрирования Business** > **портала прежних версий**.</span><span class="sxs-lookup"><span data-stu-id="72624-112">Go to the **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="72624-113">В левой панели навигации выберите пункты **голосовой связи** > **пользователей голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="72624-113">In the left navigation go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="72624-114">Позволяет параметр **голосовой связи** в левой области навигации в Скайп по центру администрирования бизнеса необходимо купить по крайней мере один **E5 корпоративной лицензии**, дополнительная лицензия на одной **Телефонной системой** или дополнительная лицензия на один **Аудио конференц-связи** .</span><span class="sxs-lookup"><span data-stu-id="72624-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="72624-115">На странице **Пользователи голосовой связи** найдите и выберите пользователя, для которого необходимо изменить адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="72624-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="72624-116">На панели действий нажмите **Местоположение для реагирования экстренных служб**, затем **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="72624-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="72624-117">На странице **Назначить номер** выберите **Изменить местоположение**.</span><span class="sxs-lookup"><span data-stu-id="72624-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="72624-118">В разделе **Изменить экстренных адрес для**введите название города, в поле и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="72624-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
8. <span data-ttu-id="72624-119">Выберите экстренных расположения в списке и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="72624-119">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="72624-120">Если вы хотите добавить новое местоположение для реагирования экстренных служб, ознакомьтесь со [Добавление, изменение или удаление местоположения для реагирования экстренных служб  для вашей организации](add-change-or-remove-an-emergency-location-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="72624-120">If you want to add a new emergency location, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="72624-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="72624-121">Related topics</span></span>
[<span data-ttu-id="72624-122">Добавление или удаление адреса для экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="72624-122">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="72624-123">Добавление, изменение и удаление местоположения организации для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="72624-123">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="72624-124">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="72624-124">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="72624-125">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="72624-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="72624-126">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="72624-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="72624-127">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="72624-127">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 