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
description: Сводка. Узнайте, как блокировать сеансы чата и конференцию в случае сбоя Skype для бизнеса Server, который предотвратит архивацию.
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095453"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="a5d39-103">Настройка параметров архива для обработки сбоев в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a5d39-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="a5d39-104">**Сводка:** Узнайте, как блокировать сеансы чата и конференцию в случае сбоя Skype для бизнеса Server, который предотвратит архивацию.</span><span class="sxs-lookup"><span data-stu-id="a5d39-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="a5d39-105">Если архивативная деятельность является требованием для вашей организации, вы можете заблокировать сеансы чата и конференцию в случае сбоя Skype для бизнес-сервера, который предотвратит архивацию.</span><span class="sxs-lookup"><span data-stu-id="a5d39-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="a5d39-106">Это иногда называется критическим режимом.</span><span class="sxs-lookup"><span data-stu-id="a5d39-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="a5d39-107">Например, при проблеме со службой хранения мгновенный доступ будет заблокирован для пользователей, чьи сообщения включены для архивирования.</span><span class="sxs-lookup"><span data-stu-id="a5d39-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="a5d39-108">Сеансы обмена мгновенными сообщениями и конференции автоматически восстанавливаются после устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="a5d39-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="a5d39-109">Настройка критического режима с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="a5d39-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="a5d39-110">Чтобы указать, следует ли разрешать сеансы связи в случае сбоя, предотвращаемого архива:</span><span class="sxs-lookup"><span data-stu-id="a5d39-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="a5d39-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5d39-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a5d39-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5d39-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a5d39-113">В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**</span><span class="sxs-lookup"><span data-stu-id="a5d39-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a5d39-114">Щелкните имя соответствующей глобальной конфигурации, сайта или пула в списке конфигураций архивации, нажмите кнопку **Изменить** и нажмите кнопку **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a5d39-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a5d39-115">Чтобы задать поведение функции архивации при сбое, установите или снимите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="a5d39-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="a5d39-116">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a5d39-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="a5d39-117">Настройка критического режима с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5d39-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="a5d39-118">Можно также указать, следует ли разрешать сеансы связи в случае сбоя, который предотвратит архивацию с помощью комлета **Set-CsArchivingConfiguration** с параметром BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="a5d39-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="a5d39-119">Например, следующая команда отключает связь в случае сбоя архива:</span><span class="sxs-lookup"><span data-stu-id="a5d39-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="a5d39-120">Следующая команда включает связь в случае сбоя архива:</span><span class="sxs-lookup"><span data-stu-id="a5d39-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="a5d39-121">Дополнительные сведения см. в разделе Справка для [cmdlet Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a5d39-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
