---
title: Проверка репликации в домене
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы убедиться в том, что подготовка домена была выполнена на этапе 1: подготовка схемы, необходимо выполнить командлет из командной консоли управления сервером Skype для Business Server Management Shell (Lync). Чтобы запустить командлет Windows PowerShell, войдите в систему на компьютере, который входит в состав домена, который вы подготовили, и в качестве участника группы администраторов домена. Выполните следующие действия.'
ms.openlocfilehash: 0b853a071116525ad313cf351685124bf92782a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303356"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="3f2c1-105">Проверка репликации в домене</span><span class="sxs-lookup"><span data-stu-id="3f2c1-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="3f2c1-106">Чтобы убедиться в том, что подготовка домена была выполнена на **этапе 1: подготовка схемы**, необходимо выполнить командлет из командной консоли управления сервером Skype для Business Server Management Shell (Lync).</span><span class="sxs-lookup"><span data-stu-id="3f2c1-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="3f2c1-107">Чтобы запустить командлет Windows PowerShell, войдите в систему на компьютере, который входит в состав домена, который вы подготовили, и в качестве участника группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="3f2c1-108">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-108">Do the following:</span></span>
  
1. <span data-ttu-id="3f2c1-109">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3f2c1-110">В Windows PowerShell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3f2c1-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="3f2c1-111">Например:</span><span class="sxs-lookup"><span data-stu-id="3f2c1-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="3f2c1-112">Параметр GlobalSettingsDomainController позволяет указать место хранения глобальных параметров.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="3f2c1-113">Если параметры хранятся в системном контейнере (обычно это происходит при развертывании обновлений без глобального параметра, перенесенного в контейнер конфигурации), вы можете определить контроллер домена в корне леса доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="3f2c1-114">Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="3f2c1-115">Если не указать этот параметр, командлет будет считать, что параметры хранятся в контейнере Configuration, и будет ссылаться на любой контроллер домена в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="3f2c1-116">Если параметр Domain не указан, в качестве значения используется локальный домен.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="3f2c1-117">В случае успешной подготовки домена этот командлет возвращает значение **LC_DOMAIN_SETTINGS_STATE_READY**.</span><span class="sxs-lookup"><span data-stu-id="3f2c1-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

