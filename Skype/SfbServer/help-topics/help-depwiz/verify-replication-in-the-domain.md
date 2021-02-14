---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: Чтобы проверить репликацию подготовки домена, выполненной на шаге 1 "Подготовка схемы", необходимо выполнить из оболочки управления Skype для бизнеса Server Lync Server. Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена. Выполните указанные ниже действия.
ms.openlocfilehash: d002a0623d6788183a5b09f8e58262fc1c68a823
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800599"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="27aed-105">Проверка репликации в домене</span><span class="sxs-lookup"><span data-stu-id="27aed-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="27aed-106">Чтобы проверить репликацию подготовки домена, выполненной на шаге **1**"Подготовка схемы", необходимо выполнить из оболочки управления Skype для бизнеса Server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27aed-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="27aed-107">Чтобы запустить Windows PowerShell, войдите на компьютер, который является членом подготовленного домена, и в качестве члена группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="27aed-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="27aed-108">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="27aed-108">Do the following:</span></span>
  
1. <span data-ttu-id="27aed-109">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="27aed-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27aed-110">В Windows PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="27aed-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="27aed-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="27aed-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="27aed-112">С помощью параметра GlobalSettingsDomainController можно указать место, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="27aed-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="27aed-113">Если параметры хранятся в контейнере System (что обычно используется в развертываниях обновления, в которых глобальный параметр не был перенесен в контейнер Configuration), необходимо определить контроллер домена в корне леса доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27aed-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="27aed-114">Если глобальные параметры размещены в контейнере конфигурации (что типично для новых или обновленных развертываний, в которых глобальный параметр был перенесен в контейнер конфигурации), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="27aed-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="27aed-115">Если этот параметр не указан, он предполагает, что параметры хранятся в контейнере Configuration и ссылаются на любой контроллер домена в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27aed-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="27aed-116">Если параметр Domain не указан, в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="27aed-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="27aed-117">Если подготовка домена прошла успешно, командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.</span><span class="sxs-lookup"><span data-stu-id="27aed-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

