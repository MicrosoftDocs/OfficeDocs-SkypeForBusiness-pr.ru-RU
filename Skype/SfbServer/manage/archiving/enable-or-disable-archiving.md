---
title: Enable or disable archiving in Skype for Business Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: Сводка. Узнайте, как включить или отключить архивировать в Skype для бизнеса Server.
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817599"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="046b6-103">Enable or disable archiving in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="046b6-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="046b6-104">**Сводка:** Узнайте, как включить или отключить архивировать в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="046b6-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="046b6-105">Включить или отключить архивировать с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="046b6-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="046b6-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="046b6-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="046b6-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="046b6-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="046b6-108">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="046b6-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="046b6-109">В списке конфигураций архивации выберите глобальную конфигурацию, конфигурацию на уровне сайта или пула, щелкните **Edit** (Изменить), щелкните **Show details** (Показать сведения) и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="046b6-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="046b6-110">Чтобы включить только архивацию сеансов обмена мгновенными сообщениями, щелкните **Archive IM sessions** (Архивировать сеансы обмена мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="046b6-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="046b6-111">Чтобы включить архивацию сеансов обмена мгновенными сообщениями и конференций, щелкните **Archive IM and conferencing sessions** (Архивировать сеансы обмена мгновенными сообщениями и конференций).</span><span class="sxs-lookup"><span data-stu-id="046b6-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="046b6-112">Чтобы отключить архивацию для конфигурации, щелкните **"Отключить архивацию".**</span><span class="sxs-lookup"><span data-stu-id="046b6-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="046b6-113">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="046b6-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="046b6-114">Включить или отключить архивировать с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="046b6-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="046b6-115">Вы также можете включить или отключить архивацию с помощью **cmdlet Set-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="046b6-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="046b6-116">Например, следующая команда изменяет все параметры конфигурации архивации, чтобы архивироваться только сеансы im.</span><span class="sxs-lookup"><span data-stu-id="046b6-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="046b6-117">Команда вызывает командлет **Get-CsArchivingConfiguration** без параметров, чтобы вернуть все параметры конфигурации архивации, в настоящее время в организации.</span><span class="sxs-lookup"><span data-stu-id="046b6-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="046b6-118">Затем эта коллекция передается в cmdlet **Where-Object,** который выбирает только те параметры, у которых свойство EnableArchiving равно (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="046b6-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="046b6-119">Затем отфильтровав коллекцию, она передается в cmdlet **Set-CsArchivingConfiguration,** который принимает каждый элемент в коллекции и изменяет значение EnableArchiving на "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="046b6-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
