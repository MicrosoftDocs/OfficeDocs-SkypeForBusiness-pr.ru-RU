---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Для проверки репликации подготовки домена, выполнить на этапе Step 1: Подготовка схемы, это необходимо для запуска командлета из Скайп для Business Server Management Shell Командная консоль Lync Server. Чтобы выполнить командлет Windows PowerShell, войдите на компьютер, который является членом домена, который вы подготовили и как член группы "Администраторы домена". Выполните следующие действия.'
ms.openlocfilehash: 32a5a315566fcee07f7214c980843829ef8e229f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234875"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="f421c-105">Проверка репликации в домене</span><span class="sxs-lookup"><span data-stu-id="f421c-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="f421c-106">Для проверки репликации подготовки домена, выполнена в **Шаг 1: Подготовка схемы**, необходимо выполнить командлет из Скайп для Business Server Management Shell Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f421c-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="f421c-107">Чтобы выполнить командлет Windows PowerShell, войдите на компьютер, который является членом домена, который вы подготовили и как член группы "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="f421c-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="f421c-108">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f421c-108">Do the following:</span></span>
  
1. <span data-ttu-id="f421c-109">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="f421c-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f421c-110">В Windows PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f421c-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="f421c-111">Например:</span><span class="sxs-lookup"><span data-stu-id="f421c-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="f421c-112">Параметр GlobalSettingsDomainController позволяет указать место хранения глобальных параметров.</span><span class="sxs-lookup"><span data-stu-id="f421c-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="f421c-113">Если параметры хранятся в контейнере System (как правило, с помощью обновления развертывания, которые не были глобальным параметром перенесенных к контейнеру конфигурации), можно определить контроллер домена в корне леса доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f421c-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="f421c-114">Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="f421c-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="f421c-115">Если не указать этот параметр, командлет будет считать, что параметры хранятся в контейнере Configuration, и будет ссылаться на любой контроллер домена в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f421c-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="f421c-116">Если параметр Domain не указан, в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="f421c-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="f421c-117">В случае успешной подготовки домена этот командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.</span><span class="sxs-lookup"><span data-stu-id="f421c-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

