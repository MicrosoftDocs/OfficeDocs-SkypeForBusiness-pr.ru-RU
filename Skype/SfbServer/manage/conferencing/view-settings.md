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
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827929"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d4269-103">Просмотр параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4269-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d4269-104">**Сводка:** Узнайте, как просматривать параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4269-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d4269-105">Параметры конфигурации собраний можно просмотреть с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4269-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4269-106">Просмотр параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4269-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="d4269-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="d4269-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="d4269-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d4269-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d4269-109">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4269-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d4269-110">В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**</span><span class="sxs-lookup"><span data-stu-id="d4269-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="d4269-111">На странице **Meeting Configuration** (Конфигурация собраний) щелкните конфигурацию собраний, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="d4269-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="d4269-112">В **фильтре "Изменить файл"** выберите **"Показать сведения".**</span><span class="sxs-lookup"><span data-stu-id="d4269-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="d4269-113">**Изменение конфигурации \<policy\> собрания -** открывает отображение параметров выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="d4269-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="d4269-114">Дополнительные сведения о настройке параметров см. в дополнительных сведениях о создании параметров конфигурации собраний [в Skype для бизнеса Server.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d4269-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4269-115">Просмотр параметров конфигурации собраний с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d4269-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="d4269-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="d4269-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="d4269-117">Чтобы просмотреть сведения обо всех параметрах конфигурации собраний, используйте **cmdlet Get-CsMeetingConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="d4269-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="d4269-118">Эта команда возвращает сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="d4269-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="d4269-119">Дополнительные сведения, включая полный список параметров, см. в подстроке [Get-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d4269-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

