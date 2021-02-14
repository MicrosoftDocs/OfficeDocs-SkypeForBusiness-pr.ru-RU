---
title: 'Конфигурация версий клиентов: создание новой или редактирование существующей'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Параметры конфигурации используются для включения и отключения управления версиями клиентов. Глобальная конфигурация версий клиентов устанавливается вместе со Skype для бизнеса Server и используется для обеспечения или отключения управления версиями клиентов для всего развертывания сервера. Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов. Вы можете отключить глобальную конфигурацию версий клиентов, если не хотите применять какое-либо управление версиями.
ms.openlocfilehash: e42d2c9e6d06bc72cd64de148454d28aab41483d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812369"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="e44d8-106">Конфигурация версий клиентов: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="e44d8-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="e44d8-107">Параметры конфигурации используются для включения и отключения управления версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="e44d8-108">Глобальная конфигурация версий клиентов устанавливается вместе со Skype для бизнеса Server и используется для обеспечения или отключения управления версиями клиентов для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="e44d8-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="e44d8-109">Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="e44d8-110">Вы можете отключить глобальную конфигурацию версий клиентов, если не хотите применять какое-либо управление версиями.</span><span class="sxs-lookup"><span data-stu-id="e44d8-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="e44d8-p103">Вы также можете создать конфигурации версий клиентов для индивидуальных сайтов, что позволяет включать и отключать управление версиями клиентов для отдельного сайта. Конфигурации для индивидуальных сайтов имеют приоритет над глобальной конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="e44d8-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e44d8-113">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="e44d8-113">Tasks you can perform</span></span>

<span data-ttu-id="e44d8-114">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="e44d8-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="e44d8-115">Добавление или изменение имени конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="e44d8-116">Включение или отключение управления версиями клиентов на глобальном уровне или для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="e44d8-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="e44d8-117">Добавление или изменение действия по умолчанию для конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e44d8-118">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="e44d8-118">UI Reference</span></span>

<span data-ttu-id="e44d8-119">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="e44d8-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="e44d8-120">**Область действия** Определяет область (глобальную или на уровне сайта) конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="e44d8-121">**Имя** Можно добавить или изменить имя конфигурации версии клиента.</span><span class="sxs-lookup"><span data-stu-id="e44d8-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="e44d8-122">**Включить управление версиями** Вы можете включить или отключить управление версиями клиентов глобально или для сайта в зависимости от области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e44d8-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="e44d8-123">**Действие по умолчанию** Можно выбрать действие по умолчанию, которое будет применяться при попытке пользователя войти в систему с помощью клиентского приложения, для которого нет определенной политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="e44d8-124">Возможны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="e44d8-124">You have the following options:</span></span>

  - <span data-ttu-id="e44d8-125">**Разрешить** Позволяет клиенту войти в систему, если версия клиента не соответствует ниому фильтру в списке политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="e44d8-126">**Block** Не позволяет клиенту войти в систему, если версия клиента не соответствует ниому фильтру в списке политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="e44d8-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="e44d8-127">**Блокировка с URL-адресом** Не позволяет клиенту войти в систему, если версия клиента не соответствует ниому фильтру в списке политик версий клиентов, и содержит сообщение об ошибке, содержащее URL-адрес для загрузки более нового клиента.</span><span class="sxs-lookup"><span data-stu-id="e44d8-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="e44d8-128">**Разрешить с URL-адресом** Позволяет клиенту войти в систему, если версия клиента не соответствует ниому фильтру в списке политик версий клиентов, и содержит сообщение об ошибке, содержащее URL-адрес для загрузки более нового клиента.</span><span class="sxs-lookup"><span data-stu-id="e44d8-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="e44d8-129">**URL-адрес** Если выбран  блок с URL-адресом или разрешить с URL-адресом, вы можете указать URL-адрес загрузки клиента, который необходимо включить в сообщение об ошибке. </span><span class="sxs-lookup"><span data-stu-id="e44d8-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="e44d8-130">Подробные сведения о взаимосвязи между клиентами [](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) и версиями клиентов см. в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e44d8-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e44d8-131">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="e44d8-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

