---
title: Создание конфигурации архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Сводка: сведения о том, как создать конфигурацию архивации для Skype для бизнеса Server.'
ms.openlocfilehash: bd2a139e7321542e3b13259ebc2ec1e4ba731caf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992746"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="9b2e6-103">Создание конфигурации архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9b2e6-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="9b2e6-104">**Сводка:** Сведения о том, как создать конфигурацию архивации для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="9b2e6-105">Настройка параметров архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="9b2e6-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="9b2e6-106">Чтобы настроить параметры архивации для определенного сайта или пула, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="9b2e6-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9b2e6-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9b2e6-109">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="9b2e6-110">На странице **Конфигурация архивации** нажмите **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="9b2e6-111">Чтобы создать конфигурацию архивации сайта, нажмите на элемент **Конфигурация сайта**, а затем в разделе **выбора сайта** выберите сайт, который требуется настроить для архивации.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="9b2e6-112">Чтобы создать конфигурацию архивации пула, нажмите на элемент **Конфигурация пула**, а затем в разделе **выбора пула** выберите пул, который требуется настроить для архивации.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="9b2e6-113">В разделе **Создание новой настройки архивации**, в раскрывающемся списке **Настройки архивации** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="9b2e6-114">Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, нажмите **Архивировать сеансы мгновенных сообщений**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="9b2e6-115">Чтобы включить архивирование для обмена мгновенными сообщениями и веб-конференций, нажмите элемент **Архивировать сеансы мгновенных сообщений и веб-конференций**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="9b2e6-116">Чтобы отключить возможность архивации для данной конфигурации, нажмите **Отключить архивацию**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="9b2e6-117">Также в разделе **Создание новой настройки архивации** выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="9b2e6-118">Для запрета действия при невозможности архивации установите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="9b2e6-119">Чтобы использовать сервер Microsoft Exchange для хранения данных для архивации, установите флажок **интеграция Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="9b2e6-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="9b2e6-120">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="9b2e6-121">Для настройки удаления записей по истечении заданного срока (в днях) щелкните **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="9b2e6-122">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="9b2e6-123">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="9b2e6-124">Настройка параметров архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b2e6-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="9b2e6-125">Параметры архивации с помощью командлета **New-CsArchivingConfiguration** также можно настроить для определенного сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="9b2e6-126">Следующая команда создает новую коллекцию параметров конфигурации архивации для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="9b2e6-127">Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="9b2e6-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="9b2e6-p101">Чтобы создать параметры, использующие разные значения свойств, просто укажите соответствующий параметр и его значение. В примере ниже представлено создание коллекции настроек параметров конфигурации, которые по умолчанию позволяют выполнять архивирование только сеансов обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-p101">To create settings that use different property values, simply include the appropriate parameter and parameter value. The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="9b2e6-p102">Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, следующая команда настраивает новые параметры для архивации сеансов обмена мгновенными сообщениями и для блокирования обмена мгновенными сообщениями при недоступности службы архивации:</span><span class="sxs-lookup"><span data-stu-id="9b2e6-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="9b2e6-132">Дополнительные сведения можно найти в разделе справки по командлету [New-ксарчивингконфигуратион](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9b2e6-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
