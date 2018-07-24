---
title: Настройка списка смарт-контактов в Скайп пользователей
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Сводка: Узнайте, как включить функцию списка смарт-контакты в Скайп для клиента Business.'
ms.openlocfilehash: 72e8a2e5eb0640215ac4512ff210d30f31295fd8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976214"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="e942f-103">Настройка списка смарт-контактов в Скайп пользователей</span><span class="sxs-lookup"><span data-stu-id="e942f-103">Configure Smart contacts list in Skype for Business clients</span></span>
 
<span data-ttu-id="e942f-104">**Сводка:** Узнайте, как включить функцию списка смарт-контакты в Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="e942f-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>
  
<span data-ttu-id="e942f-105">Функция интеллектуального списка контактов позволяет автоматически заполнять списки контактов для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e942f-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="e942f-106">При первом использовании Скайп для бизнеса, пользователи будут автоматически см их manager и других пользователей в своей группы.</span><span class="sxs-lookup"><span data-stu-id="e942f-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="e942f-107">Эта функция включена по умолчанию для пользователей Office 365, но необходимо явно включить этот компонент для локальных пользователей, настроив параметр политики клиента.</span><span class="sxs-lookup"><span data-stu-id="e942f-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>
  
<span data-ttu-id="e942f-108">При настройке этого компонента следует учитывать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="e942f-108">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="e942f-109">Пользователи, до 13, автоматически добавляются в список контактов смарт-в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="e942f-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>
    
  1. <span data-ttu-id="e942f-110">Директор</span><span class="sxs-lookup"><span data-stu-id="e942f-110">Manager</span></span>
    
  2. <span data-ttu-id="e942f-111">Непосредственные руководители в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="e942f-111">Directs in alphabetical order</span></span>
    
  3. <span data-ttu-id="e942f-112">Коллеги в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="e942f-112">Peers in alphabetical order</span></span>
    
- <span data-ttu-id="e942f-113">При первом входе пользователя создается новая группа "Моя группа".</span><span class="sxs-lookup"><span data-stu-id="e942f-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="e942f-114">Группе автоматически заполняется людей в связь группы AD пользователя на основании псевдоним пользователя, в поле Manager.</span><span class="sxs-lookup"><span data-stu-id="e942f-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="e942f-115">Обратите внимание, что после исходного заполнения группы "Моя группа" ее состав не меняется при изменении членства в группе AD.</span><span class="sxs-lookup"><span data-stu-id="e942f-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="e942f-116">Если пользователь удаляет контакт или группу, ни контакт, ни группа не создаются заново.</span><span class="sxs-lookup"><span data-stu-id="e942f-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 
    
- <span data-ttu-id="e942f-117">Если автоматическая расстановка тегов включена, контакты в данном списке отмечаются тегами в соответствии с изменением состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="e942f-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="e942f-118">Автоматическая расстановка тегов по умолчанию включена, но при желании эту функцию можно отключить.</span><span class="sxs-lookup"><span data-stu-id="e942f-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 
    
- <span data-ttu-id="e942f-119">Все новые пользователи в этой группе информируются об их добавлении в список контактов.</span><span class="sxs-lookup"><span data-stu-id="e942f-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="e942f-120">Пользователи могут вручную добавлять новых участников в свою группу "Моя группа" или другие группы по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="e942f-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>
    
- <span data-ttu-id="e942f-121">Эта функция работает только для пользователей, которые выполняют вход в первый раз.</span><span class="sxs-lookup"><span data-stu-id="e942f-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="e942f-122">Она не включена для пользователей, которые уже входили с другого устройства, включая, например, любое мобильное устройство или компьютер Mac.</span><span class="sxs-lookup"><span data-stu-id="e942f-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>
    
## <a name="configure-smart-contacts-list"></a><span data-ttu-id="e942f-123">Настройка интеллектуального списка контактов</span><span class="sxs-lookup"><span data-stu-id="e942f-123">Configure Smart contacts list</span></span>

<span data-ttu-id="e942f-124">Чтобы включить функцию интеллектуального списка контактов для пользователей, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e942f-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 
  
- <span data-ttu-id="e942f-125">Создать новую запись CsClientPolicy и добавление его в глобальной клиентской политикой.</span><span class="sxs-lookup"><span data-stu-id="e942f-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 
    
- <span data-ttu-id="e942f-126">Убедитесь в том, что поиск в адресной книге настроен только для поиска в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e942f-126">Make sure that Address Book Search is configured for Web Search only.</span></span>
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="e942f-127">Создание записи политики для активации интеллектуального списка контактов</span><span class="sxs-lookup"><span data-stu-id="e942f-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="e942f-128">Чтобы создать запись политики для включения функции списка смарт-контакты, используйте командлет [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) с параметром EnableClientAutoPopulateWithTeam следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e942f-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="e942f-129">Затем используйте командлет [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) для записи изменений в глобальной политике следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e942f-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="e942f-130">Дополнительно можно создать политику для отключения автоматической расстановки тегов:</span><span class="sxs-lookup"><span data-stu-id="e942f-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

<span data-ttu-id="e942f-131">Кроме того, для соответствующей политики параметру AddressBookAvailability необходимо задать значение WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="e942f-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="e942f-132">Дополнительные сведения см в [Командлет Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e942f-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 
  
### <a name="troubleshoot"></a><span data-ttu-id="e942f-133">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="e942f-133">Troubleshoot</span></span>

<span data-ttu-id="e942f-134">Если интеллектуальный список контактов не функционирует ожидаемым образом, выполните следующие проверки.</span><span class="sxs-lookup"><span data-stu-id="e942f-134">If Smart contacts list is not functioning as expected, check the following:</span></span>
  
- <span data-ttu-id="e942f-135">Проверьте конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e942f-135">Validate the configuration.</span></span> 
    
- <span data-ttu-id="e942f-136">Проверьте заполнение информации об организации AD.</span><span class="sxs-lookup"><span data-stu-id="e942f-136">Confirm that the AD organization information is populated.</span></span>
    
- <span data-ttu-id="e942f-137">Сбор Скайп для журналов клиента Business на нового пользователя для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="e942f-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>
    
- <span data-ttu-id="e942f-138">Убедитесь в том, что Скайп для клиента Business пользовательский Интерфейс не отображается сообщение, в котором он не удается подключиться к адресной книге.</span><span class="sxs-lookup"><span data-stu-id="e942f-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="e942f-139">Чтобы подтвердить подключение адресной книги, выполните поиск пользователя в Скайп для панели поиска клиента Business.</span><span class="sxs-lookup"><span data-stu-id="e942f-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>
    
- <span data-ttu-id="e942f-140">Проблемы репликации Доменных служб может привести к контактов, чтобы быть разрешены, когда пользователь первый раз входит в Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e942f-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>
    

