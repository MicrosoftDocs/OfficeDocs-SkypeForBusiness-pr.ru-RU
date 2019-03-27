---
title: Изменение параметров конфигурации собрания в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Сводка: Узнайте, как для изменения параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: 73127bfce04c8c124ce8036222d755de6bc37058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876050"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6c126-103">Изменение параметров конфигурации собрания в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6c126-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6c126-104">**Сводка:** Узнайте, как для изменения параметров конфигурации собрания в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c126-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="6c126-105">Вы можете изменить параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c126-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6c126-106">Изменение параметров конфигурации собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="6c126-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6c126-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6c126-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6c126-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c126-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6c126-109">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="6c126-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="6c126-110">В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="6c126-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="6c126-111">В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="6c126-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="6c126-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6c126-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6c126-113">Изменение параметров конфигурации собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="6c126-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6c126-114">Для изменения параметров конфигурации собрания используется командлет **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6c126-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6c126-p101">Приведенная в примере ниже команда изменяет назначенные сайту Redmond (-Identity site:Redmond) параметры конфигурации собраний. В данном случае свойству DesignateAsPresenter задается значение Everyone.</span><span class="sxs-lookup"><span data-stu-id="6c126-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="6c126-117">Дополнительные сведения, включая полный список параметров [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="6c126-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

