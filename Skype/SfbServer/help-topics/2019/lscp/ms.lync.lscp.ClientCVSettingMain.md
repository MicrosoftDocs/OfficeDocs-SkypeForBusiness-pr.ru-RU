---
title: Конфигурация версий клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: Кроме указания версии клиентов, поддержку которой вы хотите обеспечить в своей среде, вы можете также указать действие по умолчанию для клиентов, пока не имеющих заданной политики выбора версий. Это позволяет ограничить число используемых в среде версий клиентов, что помогает управлять затратами на поддержку нескольких версий клиентов.
ms.openlocfilehash: d2d2a18928a31d136b52a90852836db93c01ffc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812319"
---
# <a name="client-version-configuration"></a><span data-ttu-id="47a5c-104">Конфигурация версий клиентов</span><span class="sxs-lookup"><span data-stu-id="47a5c-104">Client Version Configuration</span></span>

<span data-ttu-id="47a5c-p102">Кроме указания версии клиентов, поддержку которой вы хотите обеспечить в своей среде, вы можете также указать действие по умолчанию для клиентов, пока не имеющих заданной политики выбора версий. Это позволяет ограничить число используемых в среде версий клиентов, что помогает управлять затратами на поддержку нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="47a5c-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="47a5c-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="47a5c-107">Tasks you can perform</span></span>

<span data-ttu-id="47a5c-108">На странице **Настройка версии клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="47a5c-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="47a5c-109">Изменение конфигурации версии клиента по умолчанию **(глобальная).**</span><span class="sxs-lookup"><span data-stu-id="47a5c-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="47a5c-110">создать настройку версии клиентов для конкретного сайта;</span><span class="sxs-lookup"><span data-stu-id="47a5c-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="47a5c-111">включить или отключить существующие настройки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="47a5c-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="47a5c-112">Поскольку анонимные пользователи не сопоставлены с сайтом, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="47a5c-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="47a5c-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="47a5c-113">UI Reference</span></span>

<span data-ttu-id="47a5c-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="47a5c-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="47a5c-115">**Новый** Можно создать конфигурацию версий клиентов для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="47a5c-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="47a5c-116">**Правка** Вы можете изменить параметры любой из политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="47a5c-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="47a5c-117">С помощью этой команды можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="47a5c-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="47a5c-118">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="47a5c-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="47a5c-119">**Выбрать все** Этот параметр выбирает все конфигурации версий клиентов в списке.</span><span class="sxs-lookup"><span data-stu-id="47a5c-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="47a5c-120">**Delete** Этот параметр удаляет все выбранные конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="47a5c-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="47a5c-121">**Обновление** Можно обновить список конфигурации версий клиентов, чтобы проверить состояние параметров всех конфигураций версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="47a5c-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="47a5c-122">Подробные сведения о взаимосвязи между клиентами [](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) и версиями клиентов см. в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="47a5c-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="47a5c-123">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="47a5c-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

