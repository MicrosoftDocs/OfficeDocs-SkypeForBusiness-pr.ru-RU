---
title: Перемещение конечных точек гибридного приложения в облако
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
description: Перед выводом из эксплуатации локальной среды Skype для бизнеса переместите конечную точку приложения.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656887"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="68a50-103">Перемещение конечных точек приложения перед выводом из эксплуатации локальной среды</span><span class="sxs-lookup"><span data-stu-id="68a50-103">Move hyrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="68a50-104">В этой статье описывается, как переместить необходимые конечные точки гибридного приложения в облако Microsoft перед выводом из эксплуатации локальной среды Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="68a50-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="68a50-105">Это шаг 3 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="68a50-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="68a50-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="68a50-106">Step 1.</span></span> [<span data-ttu-id="68a50-107">Перемещение всех необходимых пользователей из локальной сети в интернет</span><span class="sxs-lookup"><span data-stu-id="68a50-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="68a50-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="68a50-108">Step 2.</span></span> <span data-ttu-id="68a50-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="68a50-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="68a50-110">**Шаг 3. Перемещение конечных точек гибридного приложения из локального в online.**</span><span class="sxs-lookup"><span data-stu-id="68a50-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="68a50-111">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="68a50-111">(This article)</span></span>

- <span data-ttu-id="68a50-112">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="68a50-112">Step 4.</span></span> <span data-ttu-id="68a50-113">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="68a50-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="68a50-114">Перемещение всех необходимых конечных точек гибридного приложения из локального в online</span><span class="sxs-lookup"><span data-stu-id="68a50-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="68a50-115">Прежде чем переместить эти конечные точки в интернет, необходимо убедиться, что вы обновили записи DNS, указав на Microsoft 365 для всех доменов SIP, используемых конечными точками.</span><span class="sxs-lookup"><span data-stu-id="68a50-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="68a50-116">Невозможно создать учетные записи ресурсов в Интернете, если записи DNS указывают на локальное.</span><span class="sxs-lookup"><span data-stu-id="68a50-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="68a50-117">Дополнительные сведения см. в [переключеть гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="68a50-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="68a50-118">Извлечение и экспорт параметров конечной точки гибридного приложения на локальном сервере путем выполнения следующей локальной команды Skype для Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68a50-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="68a50-119">Создание и лицензирование новых [учетных записей](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) ресурсов в Microsoft 365 для замены существующих конечных точек гибридного приложения.</span><span class="sxs-lookup"><span data-stu-id="68a50-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="68a50-120">Связывать новые учетные записи ресурсов с существующими конечными точками гибридных приложений.</span><span class="sxs-lookup"><span data-stu-id="68a50-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="68a50-121">Удалите номера телефонов, определенные в конечных точках локального гибридного приложения, исполнив следующую команду Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68a50-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="68a50-122">Так как возможно, что номера телефонов для этих учетных записей управлялись в Microsoft 365 вместо локального, запустите следующую команду в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68a50-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="68a50-123">Назначение номеров телефонов новым учетным записям ресурсов, созданным в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="68a50-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="68a50-124">Дополнительные сведения о назначении номера телефона учетной записи ресурса см. в следующей статье: [Назначение номера службы.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="68a50-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="68a50-125">Удалите конечные точки локального сервера, исполнив следующую команду Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68a50-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="68a50-126">Теперь вы готовы удалить локальное развертывание [Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="68a50-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68a50-127">См. также</span><span class="sxs-lookup"><span data-stu-id="68a50-127">See also</span></span>

- [<span data-ttu-id="68a50-128">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="68a50-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="68a50-129">Перемещение всех необходимых пользователей из локальной сети в интернет</span><span class="sxs-lookup"><span data-stu-id="68a50-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="68a50-130">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="68a50-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="68a50-131">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="68a50-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)



