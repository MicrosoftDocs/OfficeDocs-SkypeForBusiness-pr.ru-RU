---
title: Настройка интеллектуального списка контактов в клиентах Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: Сводка. Узнайте, как включить функцию интеллектуального списка контактов в клиенте Skype для бизнеса.
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805779"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="e01b9-103">Настройка интеллектуального списка контактов в клиентах Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e01b9-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="e01b9-104">**Сводка:** Узнайте, как включить функцию интеллектуального списка контактов в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e01b9-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="e01b9-105">Функция интеллектуального списка контактов позволяет автоматически использовать списки контактов для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e01b9-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="e01b9-106">При первом использовании Skype для бизнеса ваши пользователи автоматически увидят своего руководителя и других пользователей в своей команде.</span><span class="sxs-lookup"><span data-stu-id="e01b9-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="e01b9-107">Эта функция включена по умолчанию для пользователей Microsoft 365 и Office 365, но ее необходимо явно включить для пользователей локальной сети, настроив параметр политики клиента.</span><span class="sxs-lookup"><span data-stu-id="e01b9-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="e01b9-108">При настройке этой функции следует иметь в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="e01b9-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="e01b9-109">Пользователи (до 13) автоматически добавляются в интеллектуальный список контактов в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="e01b9-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="e01b9-110">Manager</span><span class="sxs-lookup"><span data-stu-id="e01b9-110">Manager</span></span>

  2. <span data-ttu-id="e01b9-111">Directs в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="e01b9-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="e01b9-112">Одноранговая узла в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="e01b9-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="e01b9-113">При первом входе пользователя создается новая группа с именем "Моя группа".</span><span class="sxs-lookup"><span data-stu-id="e01b9-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="e01b9-114">Группа автоматически заполняется пользователями в связи группы AD пользователя на основе псевдонима пользователя, заполненного в поле "Менеджер".</span><span class="sxs-lookup"><span data-stu-id="e01b9-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="e01b9-115">Обратите внимание, что изменения членства в группе AD не приводят к обновлению группы "Моя группа" после ее первоначального заполнения.</span><span class="sxs-lookup"><span data-stu-id="e01b9-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="e01b9-116">Если пользователь удаляет контакт или группу, ни контакт, ни группа не создаются повторно.</span><span class="sxs-lookup"><span data-stu-id="e01b9-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="e01b9-117">Если автоматическое добавление тегов включено, контакты в списке будут помечены для изменения присутствия.</span><span class="sxs-lookup"><span data-stu-id="e01b9-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="e01b9-118">Автоматическое добавление тегов включено по умолчанию, но вы можете отключить его.</span><span class="sxs-lookup"><span data-stu-id="e01b9-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="e01b9-119">Все новые пользователи в группе будут добавлены в список контактов.</span><span class="sxs-lookup"><span data-stu-id="e01b9-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="e01b9-120">Пользователи могут вручную добавлять новых участников в свою группу "Моя группа" или другие группы по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="e01b9-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="e01b9-121">Эта функция работает только для пользователей, которые в первый раз в нее в первый раз.</span><span class="sxs-lookup"><span data-stu-id="e01b9-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="e01b9-122">Если пользователь ранее въехал с какого-либо устройства, включая, например, любое мобильное устройство или компьютер Mac, эта функция не включена для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e01b9-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="e01b9-123">Настройка интеллектуального списка контактов</span><span class="sxs-lookup"><span data-stu-id="e01b9-123">Configure Smart contacts list</span></span>

<span data-ttu-id="e01b9-124">Чтобы включить функцию интеллектуального списка контактов для пользователей, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e01b9-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="e01b9-125">Создайте новую запись CsClientPolicy и добавьте ее в глобальную клиентскую политику.</span><span class="sxs-lookup"><span data-stu-id="e01b9-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="e01b9-126">Убедитесь, что поиск в адресной книге настроен только для веб-поиска.</span><span class="sxs-lookup"><span data-stu-id="e01b9-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="e01b9-127">Создание записи политики для вхождения интеллектуального списка контактов</span><span class="sxs-lookup"><span data-stu-id="e01b9-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="e01b9-128">Чтобы создать запись политики, чтобы включить функцию интеллектуального списка контактов, используйте с параметром EnableClientAutoPopulateWithTeam с помощью cmdlet [New-CsClientPolicyEntry:](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e01b9-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="e01b9-129">Затем используйте для записи изменений в глобальную политику следующий код с помощью cmdlet [Set-CsClientPolicy:](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e01b9-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="e01b9-130">При желании можно создать политику для отключения автоматического маркировки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e01b9-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="e01b9-131">Также необходимо установить параметр AddressBookAvailability для соответствующей политики на WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="e01b9-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="e01b9-132">Дополнительные сведения [см. в поле Set-CsClientPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e01b9-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="e01b9-133">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="e01b9-133">Troubleshoot</span></span>

<span data-ttu-id="e01b9-134">Если интеллектуальный список контактов не работает должным образом, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="e01b9-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="e01b9-135">Проверьте конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e01b9-135">Validate the configuration.</span></span> 

- <span data-ttu-id="e01b9-136">Подтвердим, что сведения об организации AD заполнены.</span><span class="sxs-lookup"><span data-stu-id="e01b9-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="e01b9-137">Сбор журналов клиента Skype для бизнеса для нового пользователя для дальнейшего анализа.</span><span class="sxs-lookup"><span data-stu-id="e01b9-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="e01b9-138">Подтвердим, что пользовательский интерфейс клиента Skype для бизнеса не отображает сообщение о том, что не удается подключиться к адресной книге.</span><span class="sxs-lookup"><span data-stu-id="e01b9-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="e01b9-139">Чтобы подтвердить подключение к адресной книге, выполните поиск пользователя в клиентской панели поиска Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e01b9-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="e01b9-140">Проблемы с репликацией AD DS могут привести к тому, что контакты будут разрешены, когда пользователь впервые войдет в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e01b9-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


