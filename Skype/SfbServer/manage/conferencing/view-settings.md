---
title: Просмотр параметров конфигурации собрания в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Сводка: Узнайте, как для просмотра параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: d7ef617050b31bd85732ee4a30d0faaed41f50d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899400"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="36dd1-103">Просмотр параметров конфигурации собрания в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="36dd1-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="36dd1-104">**Сводка:** Узнайте, как для просмотра параметров конфигурации собрания в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dd1-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="36dd1-105">Можно просмотреть параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dd1-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="36dd1-106">Просмотр параметров конфигурации собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="36dd1-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="36dd1-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="36dd1-107"></span></span>

1. <span data-ttu-id="36dd1-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36dd1-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="36dd1-109">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dd1-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="36dd1-110">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="36dd1-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="36dd1-111">На странице **Конфигурация собрания** (Конфигурация собраний) щелкните конфигурацию собраний, которую требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="36dd1-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="36dd1-112">В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="36dd1-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="36dd1-113">\*\*Изменение конфигурации собрания - \<политики\> \*\* открывает Отображение параметров для выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="36dd1-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="36dd1-114">Для получения дополнительных сведений о настройке параметров см [параметров конфигурации в Скайп для Business Server собрания](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="36dd1-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="36dd1-115">Просмотр параметров конфигурации собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="36dd1-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="36dd1-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="36dd1-116"></span></span>

<span data-ttu-id="36dd1-117">Для просмотра сведений обо всех параметрах конфигурации собраний выполните командлет **Get-CsMeetingConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="36dd1-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="36dd1-118">Эта команда возвращает информацию следующего вида:</span><span class="sxs-lookup"><span data-stu-id="36dd1-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="36dd1-119">Дополнительные сведения, включая полный список параметров [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="36dd1-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

