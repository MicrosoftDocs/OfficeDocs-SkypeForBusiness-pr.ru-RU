---
title: Настройка списка смарт-контактов в клиентах Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Сводка: в этой статье рассказывается, как включить функцию списка смарт-контактов в клиенте Skype для бизнеса.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776694"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="a93f6-103">Настройка списка смарт-контактов в клиентах Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a93f6-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="a93f6-104">**Сводка:** Сведения о том, как включить функцию списка смарт-контактов в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a93f6-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="a93f6-105">Функция "список смарт-контактов" позволяет выполнять автоматическое заполнение списков контактов для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a93f6-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="a93f6-106">При первом использовании Skype для бизнеса пользователи будут автоматически видеть своего руководителя и других участников группы.</span><span class="sxs-lookup"><span data-stu-id="a93f6-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="a93f6-107">Эта функция включена по умолчанию для пользователей Microsoft 365 и Office 365, но необходимо явно включить эту функцию для локальных пользователей, настроив параметр политики клиента.</span><span class="sxs-lookup"><span data-stu-id="a93f6-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="a93f6-108">При настройке этой функции учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a93f6-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="a93f6-109">Пользователи, до 13, автоматически добавляются в список смарт-контактов в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="a93f6-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="a93f6-110">Директор</span><span class="sxs-lookup"><span data-stu-id="a93f6-110">Manager</span></span>

  2. <span data-ttu-id="a93f6-111">Направление в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="a93f6-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="a93f6-112">Одноранговые узлы в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="a93f6-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="a93f6-113">При первом входе пользователя создается новая группа с именем My Group.</span><span class="sxs-lookup"><span data-stu-id="a93f6-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="a93f6-114">В группу автоматически заполняются пользователи из отношения групп Active Directory пользователя, основанного на псевдониме пользователя, заполненном в поле "руководитель".</span><span class="sxs-lookup"><span data-stu-id="a93f6-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="a93f6-115">Обратите внимание, что изменения, внесенные в членство в группе Active Directory, не приводят к обновлению группы после ее первоначального заполнения.</span><span class="sxs-lookup"><span data-stu-id="a93f6-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="a93f6-116">Если пользователь удаляет контакт или группу, ни сам контакт, ни группа не будут созданы повторно.</span><span class="sxs-lookup"><span data-stu-id="a93f6-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="a93f6-117">Если включена автоматическая разметка, контакты в списке будут отмечены для изменения сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="a93f6-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="a93f6-118">Автоматическая маркировка включена по умолчанию, но ее можно отключить.</span><span class="sxs-lookup"><span data-stu-id="a93f6-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="a93f6-119">Все новые пользователи в группе получат уведомление о том, что они добавлены в список контактов.</span><span class="sxs-lookup"><span data-stu-id="a93f6-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="a93f6-120">Пользователи могут вручную добавлять новых участников в свою группу "Мои группы" или другие группы по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="a93f6-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="a93f6-121">Эта функция работает только для пользователей, выполнивших вход в первый раз.</span><span class="sxs-lookup"><span data-stu-id="a93f6-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="a93f6-122">Если пользователь ранее выполнил вход с любого устройства, включая, например, любое мобильное устройство или Mac--, эта функция не включена для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a93f6-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="a93f6-123">Настройка списка смарт-контактов</span><span class="sxs-lookup"><span data-stu-id="a93f6-123">Configure Smart contacts list</span></span>

<span data-ttu-id="a93f6-124">Чтобы включить функцию списка смарт-контактов для пользователей, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a93f6-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="a93f6-125">Создайте новую запись CsClientPolicy и добавьте ее в глобальную политику клиента.</span><span class="sxs-lookup"><span data-stu-id="a93f6-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="a93f6-126">Убедитесь, что поиск в адресной книге настроен только для поиска в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a93f6-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="a93f6-127">Создание записи политики для включения интеллектуального списка контактов</span><span class="sxs-lookup"><span data-stu-id="a93f6-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="a93f6-128">Чтобы создать запись политики для включения функции списка смарт-контактов, используйте командлет [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) с параметром EnableClientAutoPopulateWithTeam, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a93f6-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="a93f6-129">Затем используйте командлет [Set – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) для записи изменений в глобальную политику следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a93f6-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="a93f6-130">При необходимости вы можете создать политику, чтобы отключить автоматическую разметку следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a93f6-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="a93f6-131">Кроме того, необходимо задать для соответствующей политики параметр Аддрессбукаваилабилити в Вебсеарчонли.</span><span class="sxs-lookup"><span data-stu-id="a93f6-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="a93f6-132">Дополнительные сведения см. в статье [Set – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a93f6-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="a93f6-133">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a93f6-133">Troubleshoot</span></span>

<span data-ttu-id="a93f6-134">Если список смарт-контактов работает не так, как ожидалось, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="a93f6-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="a93f6-135">Проверка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a93f6-135">Validate the configuration.</span></span> 

- <span data-ttu-id="a93f6-136">Убедитесь, что заполнены сведения об организации AD.</span><span class="sxs-lookup"><span data-stu-id="a93f6-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="a93f6-137">Сбор журналов клиентов Skype для бизнеса на новом пользователе для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="a93f6-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="a93f6-138">Убедитесь, что в пользовательском интерфейсе клиента Skype для бизнеса не отображается сообщение о том, что оно не может подключиться к адресной книге.</span><span class="sxs-lookup"><span data-stu-id="a93f6-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="a93f6-139">Чтобы подтвердить подключение к адресной книге, выполните поиск пользователя на панели поиска клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a93f6-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="a93f6-140">Проблемы с репликацией AD DS могут привести к неразрешимым контактам при первом входе пользователя в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a93f6-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


