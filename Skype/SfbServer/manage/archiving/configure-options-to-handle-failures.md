---
title: Настройка параметров архивации для обработки ошибок в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: ': Сводка блокирование сеансов обмена мгновенными Сообщениями и конференц-связи в случае Скайп для сбоев Business Server, который будет препятствовать архивации.'
ms.openlocfilehash: 952ee82ca3be045fc0407a6ce2f61fdaead12030
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998716"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="26cfb-103">Настройка параметров архивации для обработки ошибок в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="26cfb-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="26cfb-104">**Сводка:** Узнайте, как для блокировки сеансов обмена мгновенными Сообщениями и конференц-связи в случае Скайп для сбоев Business Server, который будет препятствовать архивации.</span><span class="sxs-lookup"><span data-stu-id="26cfb-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="26cfb-105">Если архивация является обязательным требованием для вашей организации, можно заблокировать сеансы обмена мгновенными Сообщениями и конференц-связи в случае Скайп для сбоев Business Server, который будет препятствовать архивации.</span><span class="sxs-lookup"><span data-stu-id="26cfb-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="26cfb-106">Этот режим иногда называется критическим.</span><span class="sxs-lookup"><span data-stu-id="26cfb-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="26cfb-107">Например, в случае неполадки службы хранения данных обмен мгновенными сообщениям блокируется для тех пользователей, сообщения которых подлежат архивации.</span><span class="sxs-lookup"><span data-stu-id="26cfb-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="26cfb-108">После устранения сбоя обмен мгновенными сообщениями и конференц-связь восстанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="26cfb-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="26cfb-109">Настройка критического режима на панели управления</span><span class="sxs-lookup"><span data-stu-id="26cfb-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="26cfb-110">Для разрешения или запрета сеансов связи в случае сбоя, препятствующего архивации, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="26cfb-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="26cfb-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="26cfb-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="26cfb-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="26cfb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="26cfb-113">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="26cfb-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="26cfb-114">В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, затем щелкните **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="26cfb-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="26cfb-115">Для выбора режима архивации в случае сбоя установите или снимите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="26cfb-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="26cfb-116">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="26cfb-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="26cfb-117">Настройка критического режима с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26cfb-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="26cfb-118">Также можно указать, разрешены ли сеансов связи в случае сбоя, которое не позволит архивации с помощью командлета **Set-CsArchivingConfiguration** с параметром BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="26cfb-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="26cfb-119">Например следующая команда выключает коммуникаций в случае сбоя архивации.</span><span class="sxs-lookup"><span data-stu-id="26cfb-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="26cfb-120">При выполнении следующей команды связь после сбоя архивации разрешается:</span><span class="sxs-lookup"><span data-stu-id="26cfb-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="26cfb-121">Для получения дополнительных сведений см раздел справки для командлета [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="26cfb-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

