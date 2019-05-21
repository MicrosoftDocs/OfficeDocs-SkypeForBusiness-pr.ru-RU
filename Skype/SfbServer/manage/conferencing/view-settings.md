---
title: Просмотр параметров конфигурации собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Сводка: сведения о том, как просматривать параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: 13d91bc4c0335d8c069e0b0d9bc41efd8714f112
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280371"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e8b5a-103">Просмотр параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8b5a-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e8b5a-104">**Сводка:** Сведения о том, как просматривать параметры конфигурации собрания в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="e8b5a-105">Параметры конфигурации собраний можно просматривать с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e8b5a-106">Просмотр параметров конфигурации собрания с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8b5a-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="e8b5a-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="e8b5a-107"></span></span>

1. <span data-ttu-id="e8b5a-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e8b5a-109">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e8b5a-110">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="e8b5a-111">На странице **Конфигурация собрания** (Конфигурация собраний) щелкните конфигурацию собраний, которую требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="e8b5a-112">В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="e8b5a-113">Диалоговое окно " \*\* \<изменение\> конфигурации собрания\*\* ", в котором отображаются параметры выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="e8b5a-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="e8b5a-114">Дополнительные сведения о настройке параметров можно найти [в разделе Создание параметров конфигурации собраний в Skype для бизнеса Server](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e8b5a-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e8b5a-115">Просмотр параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e8b5a-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="e8b5a-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="e8b5a-116"></span></span>

<span data-ttu-id="e8b5a-117">Для просмотра сведений обо всех параметрах конфигурации собраний выполните командлет **Get-CsMeetingConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="e8b5a-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="e8b5a-118">Эта команда возвращает информацию следующего вида:</span><span class="sxs-lookup"><span data-stu-id="e8b5a-118">This command will return information similar to the following:</span></span>
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

<span data-ttu-id="e8b5a-119">Дополнительные сведения, включая полный список параметров, можно найти в [статьях Get-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e8b5a-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

