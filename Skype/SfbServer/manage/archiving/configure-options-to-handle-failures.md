---
title: Настройка параметров архива для обработки сбоев в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: Сводка. Узнайте, как заблокировать сеансы im и conferencing в случае сбоя Skype для бизнеса Server, который препятствует архивированию.
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817679"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="4c78a-103">Настройка параметров архива для обработки сбоев в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4c78a-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="4c78a-104">**Сводка:** Узнайте, как заблокировать сеансы im и conferencing в случае сбоя Skype для бизнеса Server, препятствующих архивированию.</span><span class="sxs-lookup"><span data-stu-id="4c78a-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="4c78a-105">Если для вашей организации существует требование к архивированию, вы можете заблокировать сеансы im и conferencing в случае сбоя Skype для бизнеса Server, который помешает архивированию.</span><span class="sxs-lookup"><span data-stu-id="4c78a-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="4c78a-106">Этот режим иногда называют критическим.</span><span class="sxs-lookup"><span data-stu-id="4c78a-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="4c78a-107">Например, при проблеме со службой хранения мгновенные сообщения будут заблокированы для пользователей, чьи коммуникации включены для архивирования.</span><span class="sxs-lookup"><span data-stu-id="4c78a-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="4c78a-108">Сеансы обмена мгновенными сообщениями и конференции автоматически восстанавливаются после устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="4c78a-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="4c78a-109">Настройка критического режима с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="4c78a-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="4c78a-110">Чтобы указать, следует ли разрешить сеансы связи в случае сбоя, препятствующих архиванию:</span><span class="sxs-lookup"><span data-stu-id="4c78a-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="4c78a-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4c78a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="4c78a-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4c78a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4c78a-113">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="4c78a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4c78a-114">Щелкните имя соответствующей глобальной конфигурации, сайта или пула в списке конфигураций архивации, нажмите кнопку "Изменить" и выберите **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="4c78a-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4c78a-115">Чтобы задать поведение функции архивации при сбое, установите или снимите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="4c78a-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="4c78a-116">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="4c78a-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="4c78a-117">Настройка критического режима с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c78a-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="4c78a-118">Можно также указать, следует ли разрешить сеансы связи в случае сбоя, который помешает архивации, с помощью cmdlet **Set-CsArchivingConfiguration** с параметром BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="4c78a-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="4c78a-119">Например, следующая команда отключает связь в случае сбоя архива:</span><span class="sxs-lookup"><span data-stu-id="4c78a-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="4c78a-120">Следующая команда включает связь в случае сбоя архива:</span><span class="sxs-lookup"><span data-stu-id="4c78a-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="4c78a-121">Дополнительные сведения см. в разделе справки по [cmdlet Set-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4c78a-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

