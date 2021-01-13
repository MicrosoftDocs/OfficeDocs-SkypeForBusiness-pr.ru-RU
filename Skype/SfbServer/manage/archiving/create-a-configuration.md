---
title: Создание конфигурации архивации в Skype для бизнеса Server
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: Сводка. Узнайте, как создать конфигурацию архивации для Skype для бизнеса Server.
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817659"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="13a9d-103">Создание конфигурации архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="13a9d-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="13a9d-104">**Сводка:** Узнайте, как создать конфигурацию архивации для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="13a9d-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="13a9d-105">Настройка параметров архива с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="13a9d-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="13a9d-106">Чтобы настроить параметры архива для определенного сайта или пула:</span><span class="sxs-lookup"><span data-stu-id="13a9d-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="13a9d-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="13a9d-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="13a9d-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="13a9d-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="13a9d-109">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="13a9d-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="13a9d-110">На странице **Конфигурация архивирования** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="13a9d-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="13a9d-111">Чтобы создать конфигурацию архивации сайта, щелкните "Конфигурация сайта", а затем в области "Выбор сайта" выберите сайт, который будет настроен для архивации.</span><span class="sxs-lookup"><span data-stu-id="13a9d-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="13a9d-112">Чтобы создать конфигурацию архивации пула, щелкните "Конфигурация пула", а затем в области "Выбор пула" выберите пул, который будет настроен для архивации.</span><span class="sxs-lookup"><span data-stu-id="13a9d-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="13a9d-113">В разделе **Новый параметр архивирования**, в раскрывающемся списке **Параметр архивирования** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="13a9d-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="13a9d-114">Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, щелкните **Архивировать сеансы обмена мгновенными сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="13a9d-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="13a9d-115">Чтобы включить архивирование для обмена мгновенными сообщениями и веб-конференций, щелкните элемент **Archive IM and web conferencing sessions** (Архивировать сеансы обмена мгновенными сообщениями и веб-конференций).</span><span class="sxs-lookup"><span data-stu-id="13a9d-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="13a9d-116">Чтобы отключить архивацию для этой конфигурации, щелкните **"Отключить архивацию".**</span><span class="sxs-lookup"><span data-stu-id="13a9d-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="13a9d-117">Также в разделе **Новый параметр архивирования** выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="13a9d-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="13a9d-118">Чтобы заблокировать действия, когда архивирование невозможно, установите флажок **Block instant messaging (IM) or web conferencing sessions if archiving fails** (Блокировать сеансы обмена мгновенными сообщениями или веб-конференций, если не удается выполнить архивирование).</span><span class="sxs-lookup"><span data-stu-id="13a9d-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="13a9d-119">Чтобы использовать Microsoft Exchange Server для хранения данных архивации, нажмите кнопку **"Интеграция Microsoft Exchange".**</span><span class="sxs-lookup"><span data-stu-id="13a9d-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="13a9d-120">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="13a9d-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="13a9d-121">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="13a9d-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="13a9d-122">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="13a9d-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="13a9d-123">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="13a9d-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="13a9d-124">Настройка параметров архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="13a9d-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="13a9d-125">Можно также настроить параметры архивации для определенного сайта или пула с помощью cmdlet **New-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="13a9d-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="13a9d-126">Следующая команда создает новую коллекцию параметров конфигурации архивации для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="13a9d-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="13a9d-127">Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="13a9d-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="13a9d-128">Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="13a9d-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="13a9d-129">В следующем примере создается коллекция параметров конфигурации архивации, которые по умолчанию позволяют архивацию только сеансов обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="13a9d-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="13a9d-p102">Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, следующая команда настраивает новые параметры для архивации сеансов обмена мгновенными сообщениями и для блокирования обмена мгновенными сообщениями при недоступности службы архивации:</span><span class="sxs-lookup"><span data-stu-id="13a9d-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="13a9d-132">Дополнительные сведения см. в разделе справки по [cmdlet New-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="13a9d-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
