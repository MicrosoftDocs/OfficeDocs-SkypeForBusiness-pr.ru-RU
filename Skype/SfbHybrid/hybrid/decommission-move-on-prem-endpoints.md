---
title: Перенос конечных точек гибридных приложений в облако
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Миграция конечных точек приложения с гидравлией до вывода из эксплуатации Skype для бизнеса локальной среды.
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420804"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="e977c-103">Перенос конечных точек гибридного приложения перед выводом из эксплуатации локальной среды</span><span class="sxs-lookup"><span data-stu-id="e977c-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="e977c-104">В этой статье описывается, как переместить необходимые конечные точки гибридных приложений в облако Майкрософт до вывода из эксплуатации локальной Skype для бизнеса среды.</span><span class="sxs-lookup"><span data-stu-id="e977c-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="e977c-105">Это шаг 3 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="e977c-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="e977c-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="e977c-106">Step 1.</span></span> [<span data-ttu-id="e977c-107">Перемещение всех необходимых пользователей из локальной сети в интернет</span><span class="sxs-lookup"><span data-stu-id="e977c-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="e977c-108">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="e977c-108">Step 2.</span></span> <span data-ttu-id="e977c-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="e977c-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="e977c-110">**Шаг 3. Перенос конечных точек гибридного приложения из локального в онлайн.**</span><span class="sxs-lookup"><span data-stu-id="e977c-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="e977c-111">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="e977c-111">(This article)</span></span>

- <span data-ttu-id="e977c-112">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="e977c-112">Step 4.</span></span> <span data-ttu-id="e977c-113">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="e977c-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="e977c-114">Перенос всех необходимых конечных точек гибридного приложения из локального в интернет</span><span class="sxs-lookup"><span data-stu-id="e977c-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="e977c-115">Прежде чем переместить эти конечные точки в интернет, необходимо убедиться, что вы обновили записи DNS, чтобы указать на Microsoft 365 для всех доменов SIP, используемых конечными точками.</span><span class="sxs-lookup"><span data-stu-id="e977c-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="e977c-116">Следует помнить, что после обновления DNS для указать на Microsoft 365, существующие конечные точки гибридных приложений больше не будут обнаруживаемыми, пока вы не выполните этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e977c-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="e977c-117">Так как этот шаг (создание учетных записей ресурсов в Интернете) невозможен, если записи DNS указывают на локальность, следует запланировать оба шага 2 и 3 в одном окне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e977c-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="e977c-118">Дополнительные сведения см. в [переключеть гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="e977c-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="e977c-119">Извлечение и экспорт параметров конечной точки гибридного приложения в локальном Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e977c-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="e977c-120">Создание и лицензирование новых [учетных](/microsoftteams/manage-resource-accounts) записей ресурсов в Microsoft 365 для замены существующих конечных точек гибридного приложения на локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="e977c-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="e977c-121">Связывать новые учетные записи ресурсов с существующими конечными точками гибридных приложений.</span><span class="sxs-lookup"><span data-stu-id="e977c-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="e977c-122">Удалите номера телефонов, определенные в конечных точках локального гибридного приложения, исполнив следующую команду Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e977c-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="e977c-123">Так как возможно, что номера телефонов для этих учетных записей управлялись в Microsoft 365, а не локально, запустите следующую команду в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e977c-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="e977c-124">Назначение номеров телефонов новым учетным записям ресурсов, созданным в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e977c-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="e977c-125">Дополнительные сведения о назначении номера телефона учетной записи ресурса см. в следующей статье: [Назначение номера службы.](/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="e977c-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="e977c-126">Удалите конечные точки на месте, исполнив следующую команду Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e977c-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="e977c-127">Теперь вы готовы [удалить локальное](decommission-remove-on-prem.md)развертывание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e977c-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e977c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e977c-128">See also</span></span>

- [<span data-ttu-id="e977c-129">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e977c-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="e977c-130">Перемещение всех необходимых пользователей из локальной сети в интернет</span><span class="sxs-lookup"><span data-stu-id="e977c-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="e977c-131">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="e977c-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="e977c-132">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e977c-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




