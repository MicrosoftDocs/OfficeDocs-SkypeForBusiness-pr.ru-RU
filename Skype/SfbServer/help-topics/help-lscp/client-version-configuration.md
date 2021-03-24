---
title: Конфигурация версий клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Кроме указания версии клиентов, поддержку которой вы хотите обеспечить в своей среде, вы можете также указать действие по умолчанию для клиентов, пока не имеющих заданной политики выбора версий. Это позволяет ограничить число используемых в среде версий клиентов, что помогает управлять затратами на поддержку нескольких версий клиентов.
ms.openlocfilehash: 31facafd00a25993aa16f5d89b1fad5a97e566a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095623"
---
# <a name="client-version-configuration"></a><span data-ttu-id="6707a-104">Конфигурация версий клиентов</span><span class="sxs-lookup"><span data-stu-id="6707a-104">Client Version Configuration</span></span>

<span data-ttu-id="6707a-p102">Кроме указания версии клиентов, поддержку которой вы хотите обеспечить в своей среде, вы можете также указать действие по умолчанию для клиентов, пока не имеющих заданной политики выбора версий. Это позволяет ограничить число используемых в среде версий клиентов, что помогает управлять затратами на поддержку нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="6707a-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6707a-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="6707a-107">Tasks you can perform</span></span>

<span data-ttu-id="6707a-108">На странице **Настройка версии клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6707a-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="6707a-109">Изменение конфигурации клиентской версии по умолчанию **(глобальная).**</span><span class="sxs-lookup"><span data-stu-id="6707a-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="6707a-110">создать настройку версии клиентов для конкретного сайта;</span><span class="sxs-lookup"><span data-stu-id="6707a-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="6707a-111">включить или отключить существующие настройки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="6707a-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="6707a-112">Поскольку анонимные пользователи не сопоставлены с сайтом, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="6707a-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6707a-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="6707a-113">UI Reference</span></span>

<span data-ttu-id="6707a-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="6707a-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6707a-115">**Новые** Можно создать конфигурацию клиентской версии для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="6707a-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="6707a-116">**Изменение** Вы можете изменить параметры любой из политик клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="6707a-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="6707a-117">С помощью этой команды можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6707a-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="6707a-118">**Демонстрация сведений** Этот параметр открывает диалоговое окно, в котором можно изменить параметры конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="6707a-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="6707a-119">**Выберите все** Этот параметр выбирает все конфигурации клиентской версии в списке.</span><span class="sxs-lookup"><span data-stu-id="6707a-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="6707a-120">**Удаление** Этот параметр удаляет все выбранные конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="6707a-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="6707a-121">**Обновление** Вы можете обновить список конфигурации клиентской версии, чтобы проверить состояние параметров всех конфигураций клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="6707a-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="6707a-122">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="6707a-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="6707a-123">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="6707a-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>