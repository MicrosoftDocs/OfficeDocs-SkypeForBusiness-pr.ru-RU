---
title: Включение или отключение архивации в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Сводка: Узнайте, как включить или отключить архивацию в Скайп Business Server 2015.'
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="83e3b-103">Включение или отключение архивации в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="83e3b-103">Enable or disable archiving in Skype for Business Server 2015</span></span>

<span data-ttu-id="83e3b-104">**Сводка:** Узнайте, как включить или отключить архивацию в Скайп Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="83e3b-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server 2015.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="83e3b-105">Включение и отключение архивации с панели управления</span><span class="sxs-lookup"><span data-stu-id="83e3b-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="83e3b-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="83e3b-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="83e3b-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="83e3b-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="83e3b-108">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="83e3b-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="83e3b-109">Выберите в списке конфигураций архивации подходящую глоабальную конфигурацию либо конфигурацию сайта или пула, щелкните **Правка**, **Подробнее**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="83e3b-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="83e3b-110">Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, нажмите **Архивировать сеансы мгновенных сообщений**.</span><span class="sxs-lookup"><span data-stu-id="83e3b-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="83e3b-111">Если требуется архивировать как сеансы обмена мгновенными сообщениями, так и конференции, щелкните **Архивировать сеансы мгновенных сообщений и веб-конференций**.</span><span class="sxs-lookup"><span data-stu-id="83e3b-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="83e3b-112">Если для данной конфигурации архивация не требуется, щелкните **Отключить архивацию**.</span><span class="sxs-lookup"><span data-stu-id="83e3b-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="83e3b-113">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="83e3b-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="83e3b-114">Включение и отключение архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83e3b-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="83e3b-115">Можно также включить или отключить архивацию с помощью командлета **Set-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="83e3b-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="83e3b-116">Например, следующая команда позволяет изменить все параметры конфигурации архивации таким образом, что архивироваться будут только сеансы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="83e3b-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="83e3b-117">Команда вызывает командлет **Get-CsArchivingConfiguration** без параметров для возврата всех параметров конфигурации архивации в настоящее время используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="83e3b-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="83e3b-118">Этот набор затем передается в командлет **Where-Object** , который выбирает только параметры, где свойство EnableArchiving равно (-eq) «ImAndWebConf».</span><span class="sxs-lookup"><span data-stu-id="83e3b-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="83e3b-119">Отфильтрованный набор затем передается в командлет **Set-CsArchivingConfiguration** , который принимает каждого элемента в коллекции и изменяет значение EnableArchiving «ImOnly»:</span><span class="sxs-lookup"><span data-stu-id="83e3b-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```