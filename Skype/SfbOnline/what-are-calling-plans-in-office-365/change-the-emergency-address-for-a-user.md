---
title: Изменение адреса экстренного реагирования для пользователя
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 'Просмотрите инструкции по изменению адреса для экстренного реагирования для пользователя для работы с телефонной сетью общего пользования (PSTN) в США и Европе. '
ms.openlocfilehash: 5f08e7503e95028e5045404dc4a0ba294addd481
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860552"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="5a837-103">Изменение адреса экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="5a837-103">Change the emergency address for a user</span></span>

<span data-ttu-id="5a837-104">При установке тарифных планов в Office 365, необходимо назначитьадрес для экстренного реагирования для каждого номера телефона или пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a837-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="5a837-105">В странах Европы адрес для экстренного реагирования связан с номером телефона при переходе с Office 365 или при перемещении номера телефона по Office 365.</span><span class="sxs-lookup"><span data-stu-id="5a837-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="5a837-106">В Соединенных Штатах Америки адрес для экстренного реагирования связан с номером телефона при назначении пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a837-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="5a837-107">Адрес для экстренного реагирования может быть изменен, если пользователь, которому он назначен перемещается в новое местоположение.</span><span class="sxs-lookup"><span data-stu-id="5a837-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="5a837-108">Для получения дополнительных сведений об адресах и местоположениях для экстренного реагирования см. раздел Что такое местоположение и адреса для реагирования экстренных служб, а также маршрутизация экстренных вызовов?[ ](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="5a837-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing) for details.</span></span>
  
<span data-ttu-id="5a837-109">Чтобы узнать о том, как получить тарифные планы Office 365 и их стоимость, см. раздел [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5a837-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="5a837-110">Изменение адреса экстренного реагирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="5a837-110">Change the emergency address for a user</span></span>

<span data-ttu-id="5a837-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="5a837-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="5a837-112">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="5a837-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5a837-113">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="5a837-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5a837-114">На левой панели навигации выберите **Голосовая связь** >  **Пользователи голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="5a837-114">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a837-115">Чтобы на левой панели навигации центра администрирования Skype для бизнеса появился элемент **Голосовая связь**, необходимо приобрести хотя бы одну **лицензию уровня корпоративный E5**, лицензию на надстройку **Телефонная система** либо лицензию на надстройку **Аудиоконференция**.</span><span class="sxs-lookup"><span data-stu-id="5a837-115">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="5a837-116">На странице **Пользователи голосовой связи** найдите и выберите пользователя, для которого необходимо изменить адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="5a837-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="5a837-117">На панели действий в разделе **Местоположение для реагирования экстренных служб** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5a837-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="5a837-118">На странице **Назначить номер** выберите **Изменить местоположение**.</span><span class="sxs-lookup"><span data-stu-id="5a837-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="5a837-119">В разделе **Изменить адрес для экстренного реагирования на**, укажите название города и нажмите **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="5a837-119">Under **Change emergency address to** put the name of the city in the Find City box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a837-120">Можно изменить только уже проверенный адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="5a837-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="5a837-121">Чтобы изменить адрес для экстренного реагирования, который еще не был проверен, удалите его и создайте другой адрес для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="5a837-121">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="5a837-122">Выберите новый адрес для экстренного реагирования в списке и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5a837-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5a837-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a837-123">Related topics</span></span>
[<span data-ttu-id="5a837-124">Добавление или удаление адреса экстренного реагирования для организации</span><span class="sxs-lookup"><span data-stu-id="5a837-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="5a837-125">Добавление, изменение и удаление местоположения организации для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="5a837-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="5a837-126">Что такое проверка адреса?</span><span class="sxs-lookup"><span data-stu-id="5a837-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="5a837-127">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="5a837-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="5a837-128">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="5a837-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="5a837-129">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5a837-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 