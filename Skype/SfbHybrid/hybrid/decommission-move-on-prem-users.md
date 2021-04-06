---
title: Перемещение пользователей и конечных точек в облако
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
description: Перемещение пользователей и конечных точек перед списанием локальной среды Skype для бизнеса.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593912"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="03262-103">Перемещение необходимых пользователей и конечных точек перед списанием локальной среды</span><span class="sxs-lookup"><span data-stu-id="03262-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="03262-104">В этой статье описывается, как переместить необходимые пользователи и конечные точки приложений в облако Microsoft перед выводом из эксплуатации локальной среды Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="03262-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="03262-105">Это шаг 1 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="03262-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="03262-106">**Шаг 1. Перемещение всех необходимых пользователей и конечных точек приложения из локальной сети в интернет.**</span><span class="sxs-lookup"><span data-stu-id="03262-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="03262-107">(В этой статье.)</span><span class="sxs-lookup"><span data-stu-id="03262-107">(This article.)</span></span>

- <span data-ttu-id="03262-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="03262-108">Step 2.</span></span> <span data-ttu-id="03262-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="03262-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="03262-110">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="03262-110">Step 3.</span></span> <span data-ttu-id="03262-111">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="03262-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="03262-112">Перемещение всех необходимых пользователей из локального в облако</span><span class="sxs-lookup"><span data-stu-id="03262-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="03262-113">Все пользователи, которые будут продолжать использовать после завершения миграции, сначала должны быть перемещены из локального в облако.</span><span class="sxs-lookup"><span data-stu-id="03262-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="03262-114">Перемещение пользователей с помощью средств администрирования на месте.</span><span class="sxs-lookup"><span data-stu-id="03262-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="03262-115">Подробные сведения см. в [материале Перемещение пользователей между локальной и облачной.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="03262-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="03262-116">Несмотря на то, что пользователи с учетными записями Skype для бизнеса Server могут использовать Teams, эти пользователи не имеют полных функциональных возможностей Teams.</span><span class="sxs-lookup"><span data-stu-id="03262-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="03262-117">Эти пользователи не могут скооперироваться или федератироваться с любым другим пользователем, все еще использующим Skype для бизнеса (будь то онлайн или локально).</span><span class="sxs-lookup"><span data-stu-id="03262-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="03262-118">Эти пользователи также не могут принимать вызовы PSTN в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="03262-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="03262-119">Поэтому необходимо переместить этих пользователей в интернет.</span><span class="sxs-lookup"><span data-stu-id="03262-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="03262-120">Этот шаг также обеспечивает перенос контактов или собраний, созданных в Skype для бизнеса Server, в Teams.</span><span class="sxs-lookup"><span data-stu-id="03262-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="03262-121">Чтобы проверить, есть ли в локальном развертывании оставшиеся пользователи, запустите следующий комдлет в окне Skype для бизнеса Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03262-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="03262-122">Если какие-либо пользователи возвращаются, просмотрите вывод, чтобы определить, следует ли какие-либо учетные записи быть перемещены в облако, и для любых таких пользователей выполните действия [здесь](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="03262-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="03262-123">Для учетных записей пользователей, которые больше не нужны, запустите следующий комдлет Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03262-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="03262-124">Запуск Disable-CsUser удаляет все атрибуты Skype для бизнеса для всех пользователей, которые соответствуют критериям фильтрации.</span><span class="sxs-lookup"><span data-stu-id="03262-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="03262-125">Перед началом процедуры подтвердим, что эти учетные записи больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="03262-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="03262-126">Перемещение конечных точек гибридного приложения в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03262-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="03262-127">Извлечение и экспорт параметров конечной точки гибридного приложения на локальном сервере путем выполнения следующей локальной команды Skype для Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03262-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="03262-128">Создание и лицензирование новых [учетных записей](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) ресурсов в Microsoft 365 для замены существующих конечных точек гибридного приложения.</span><span class="sxs-lookup"><span data-stu-id="03262-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="03262-129">Связывать новые учетные записи ресурсов с существующими конечными точками гибридных приложений.</span><span class="sxs-lookup"><span data-stu-id="03262-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="03262-130">Удалите номера телефонов, определенные в конечных точках локального гибридного приложения, исполнив следующую команду Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03262-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="03262-131">Так как возможно, что номера телефонов для этих учетных записей управлялись в Microsoft 365 вместо локального, запустите следующую команду в Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03262-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="03262-132">Назначение номеров телефонов новым учетным записям ресурсов, созданным в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="03262-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="03262-133">Дополнительные сведения о назначении номера телефона учетной записи ресурса см. в следующей статье: [Назначение номера службы.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="03262-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="03262-134">Удалите конечные точки локального сервера, исполнив следующую команду Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03262-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="03262-135">Теперь вы готовы отключить [гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="03262-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="03262-136">См. также</span><span class="sxs-lookup"><span data-stu-id="03262-136">See also</span></span>

- [<span data-ttu-id="03262-137">Вывод из эксплуатации локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="03262-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="03262-138">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="03262-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="03262-139">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="03262-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




