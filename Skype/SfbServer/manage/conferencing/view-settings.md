---
title: Просмотр параметров конфигурации собраний в Skype для бизнеса Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: Сводка. Сведения о просмотре параметров конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096705"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="36611-103">Просмотр параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="36611-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="36611-104">**Сводка:** Узнайте, как просматривать параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="36611-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="36611-105">Параметры конфигурации собраний можно просматривать с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="36611-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="36611-106">Просмотр параметров конфигурации собраний с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="36611-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="36611-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="36611-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="36611-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36611-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="36611-109">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="36611-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="36611-110">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.</span><span class="sxs-lookup"><span data-stu-id="36611-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="36611-111">На странице **Meeting Configuration** (Конфигурация собраний) щелкните конфигурацию собраний, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="36611-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="36611-112">В **фильтре редактирования файла** выберите поле **"Сведения** о шоу".</span><span class="sxs-lookup"><span data-stu-id="36611-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="36611-113">**Изменение конфигурации \<policy\> собраний —** открывает отображение параметров выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="36611-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="36611-114">Дополнительные сведения о настройке параметров см. в материале [Create meeting configuration settings in Skype for Business Server.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="36611-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="36611-115">Просмотр параметров конфигурации собраний с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="36611-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="36611-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="36611-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="36611-117">Чтобы просмотреть сведения обо всех параметрах конфигурации собраний, используйте комлет **Get-CsMeetingConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="36611-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="36611-118">Эта команда возвращает сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="36611-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="36611-119">Дополнительные сведения, включая полный список параметров, см. в [списке Get-CsMeetingConfiguration.](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="36611-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
