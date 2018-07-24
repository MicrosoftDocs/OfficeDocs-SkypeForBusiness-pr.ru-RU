---
title: Создание новой или редактирование существующей конфигурации версий клиентов
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Параметры конфигурации используются для включения и отключения управления версиями клиентов. Конфигурация версии клиента глобального устанавливается с Скайп для Business Server и используется для включения или отключения контроля версий клиента для развертывания всего сервера. Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов. Вы можете отключить глобальную конфигурацию версий клиентов, если не хотите применять какое-либо управление версиями.
ms.openlocfilehash: a5647926d8fca4548dd376da6218e6f9aac27d3c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983772"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="3fcde-106">Конфигурация версии клиента: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="3fcde-106">Client Version Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="3fcde-107">Параметры конфигурации используются для включения и отключения управления версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="3fcde-108">Конфигурация версии клиента глобального устанавливается с Скайп для Business Server и используется для включения или отключения контроля версий клиента для развертывания всего сервера.</span><span class="sxs-lookup"><span data-stu-id="3fcde-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="3fcde-109">Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="3fcde-110">Вы можете отключить глобальную конфигурацию версий клиентов, если не хотите применять какое-либо управление версиями.</span><span class="sxs-lookup"><span data-stu-id="3fcde-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span> 
  
<span data-ttu-id="3fcde-p103">Вы также можете создать конфигурации версий клиентов для индивидуальных сайтов, что позволяет включать и отключать управление версиями клиентов для отдельного сайта. Конфигурации для индивидуальных сайтов имеют приоритет над глобальной конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="3fcde-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="3fcde-113">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="3fcde-113">Tasks you can perform</span></span>

<span data-ttu-id="3fcde-114">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="3fcde-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="3fcde-115">Добавление или изменение имени конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-115">Add or modify the name of the client version configuration.</span></span>
    
- <span data-ttu-id="3fcde-116">Включение или отключение управления версиями клиентов на глобальном уровне или для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="3fcde-116">Enable or disable client version control globally or for the specific site.</span></span>
    
- <span data-ttu-id="3fcde-117">Добавление или изменение действия по умолчанию для конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-117">Add or modify the default action for the client version configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="3fcde-118">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="3fcde-118">UI Reference</span></span>

<span data-ttu-id="3fcde-119">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3fcde-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="3fcde-120">**Область** Определяет область (глобальную или сайтов) конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>
    
- <span data-ttu-id="3fcde-121">**Имя** Вы можете добавить или изменить имя конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-121">**Name** You can add or modify the name of the client version configuration.</span></span>
    
- <span data-ttu-id="3fcde-122">**Включение управления версиями** Можно включить или отключить управление версиями клиентов глобальном уровне или для сайта, в зависимости от области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3fcde-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>
    
- <span data-ttu-id="3fcde-123">**Действие по умолчанию** Можно выбрать действие по умолчанию, который будет применяться, когда пользователь пытается выполнить вход с помощью клиентского приложения, для которого отсутствует политика версии конкретного клиента.</span><span class="sxs-lookup"><span data-stu-id="3fcde-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="3fcde-124">Возможны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="3fcde-124">You have the following options:</span></span>
    
  - <span data-ttu-id="3fcde-125">**Разрешить** Разрешает клиенту выполнить вход, если версия клиента не соответствует ни одному фильтру в списке политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>
    
  - <span data-ttu-id="3fcde-126">**Блок** Запрещает клиенту вход в систему, если версия клиента не соответствует ни одному фильтру в списке политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3fcde-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>
    
  - <span data-ttu-id="3fcde-127">**Блокировать с URL-адреса** Запрещает клиенту вход в систему, если версия клиента не соответствует ни одному фильтру в списке политик версий клиентов, а также содержит сообщение об ошибке, содержащее URL-адрес, где можно загрузить более новая версия клиента.</span><span class="sxs-lookup"><span data-stu-id="3fcde-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>
    
  - <span data-ttu-id="3fcde-128">**Разрешить с URL-адресом** Разрешает клиенту выполнить вход, если версия клиента не соответствует ни одному фильтру в списке политик версий клиентов, а также содержит сообщение об ошибке, содержащая URL-адрес, где можно загрузить более новая версия клиента.</span><span class="sxs-lookup"><span data-stu-id="3fcde-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>
    
  - <span data-ttu-id="3fcde-129">**URL-адрес** Если выбрано **Блокировать с URL-адресом** или **Разрешить с URL-адресом**, можно указать URL-адрес загрузки клиента необходимо включить в сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="3fcde-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>
    
<span data-ttu-id="3fcde-130">Для получения дополнительных сведений о взаимодействии между клиентами и их версий в документации по планированию показано [Взаимодействие с клиентом](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3fcde-130">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="3fcde-131">Для получения дополнительных сведений о работе с настройки версий клиентов видеть [Изменение действия по умолчанию для клиентов не явным образом поддерживается "или" Ограниченные](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="3fcde-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

