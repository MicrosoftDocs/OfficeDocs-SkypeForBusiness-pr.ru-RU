---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Для проверки репликации подготовки домена, выполнить на этапе Step 1: Подготовка схемы, это необходимо для запуска командлета из Скайп для Business Server Management Shell Командная консоль Lync Server. Чтобы выполнить командлет Windows PowerShell, войдите на компьютер, который является членом домена, который вы подготовили и как член группы "Администраторы домена". Выполните следующие действия.'
ms.openlocfilehash: 1c23266b82e0f0a76f075c50509b43210a35bfd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893632"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="9b66a-105">Проверка репликации в домене</span><span class="sxs-lookup"><span data-stu-id="9b66a-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="9b66a-106">Для проверки репликации подготовки домена, выполнена в **Шаг 1: Подготовка схемы**, необходимо выполнить командлет из Скайп для Business Server Management Shell Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b66a-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="9b66a-107">Чтобы выполнить командлет Windows PowerShell, войдите на компьютер, который является членом домена, который вы подготовили и как член группы "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="9b66a-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="9b66a-108">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b66a-108">Do the following:</span></span>
  
1. <span data-ttu-id="9b66a-109">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9b66a-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9b66a-110">В Windows PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9b66a-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="9b66a-111">Например:</span><span class="sxs-lookup"><span data-stu-id="9b66a-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="9b66a-112">Параметр GlobalSettingsDomainController позволяет указать место хранения глобальных параметров.</span><span class="sxs-lookup"><span data-stu-id="9b66a-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="9b66a-113">Если параметры хранятся в контейнере System (как правило, с помощью обновления развертывания, которые не были глобальным параметром перенесенных к контейнеру конфигурации), можно определить контроллер домена в корне леса доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9b66a-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="9b66a-114">Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="9b66a-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="9b66a-115">Если не указать этот параметр, командлет будет считать, что параметры хранятся в контейнере Configuration, и будет ссылаться на любой контроллер домена в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9b66a-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="9b66a-116">Если параметр Domain не указан, в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="9b66a-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="9b66a-117">В случае успешной подготовки домена этот командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.</span><span class="sxs-lookup"><span data-stu-id="9b66a-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

