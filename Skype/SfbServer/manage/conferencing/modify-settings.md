---
title: Изменение параметров конфигурации собраний в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Сводка: Узнайте, как для изменения параметров конфигурации собрания в Скайп для Business Server 2015.'
ms.openlocfilehash: 95f28f35859553f79fc6f74f8850f224bda54deb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="75819-103">Изменение параметров конфигурации собраний в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="75819-103">Modify meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="75819-104">**Сводка:** Узнайте, как для изменения параметров конфигурации собрания в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="75819-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="75819-105">Вы можете изменить параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="75819-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="75819-106">Изменение параметров конфигурации собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="75819-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="75819-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="75819-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="75819-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="75819-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="75819-109">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="75819-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="75819-110">В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="75819-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="75819-111">В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="75819-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="75819-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="75819-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="75819-113">Изменение параметров конфигурации собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="75819-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="75819-114">Для изменения параметров конфигурации собрания используется командлет **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="75819-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="75819-p101">Приведенная в примере ниже команда изменяет назначенные сайту Redmond (-Identity site:Redmond) параметры конфигурации собраний. В данном случае свойству DesignateAsPresenter задается значение Everyone.</span><span class="sxs-lookup"><span data-stu-id="75819-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="75819-117">Дополнительные сведения, включая полный список параметров [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="75819-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

