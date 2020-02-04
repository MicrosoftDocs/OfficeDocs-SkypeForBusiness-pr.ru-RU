---
title: Тестовое устройство создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: Возможность "Устройство проверки" работает совместно с возможностью "Обновление устройства". Вы можете добавить устройство проверки на страницу Устройство проверки и затем использовать его для проверки функциональных возможностей новых обновлений перед их развертыванием на производственных устройствах. Вы можете протестировать устройство глобально (то есть в рамках всей среды) или для отдельного сайта. Устройство проверки указывается по MAC-адресу или серийному номеру. После добавления устройства оно появится в списке на странице "тестирование устройства" на панели управления "Skype для бизнеса Server".
ms.openlocfilehash: 56f5c7b43f55f50c5fa5e73cade3f74bea752778
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699471"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="d1087-107">Тестовое устройство: создание нового или редактирование существующего</span><span class="sxs-lookup"><span data-stu-id="d1087-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="d1087-108">Возможность "Устройство проверки" работает совместно с возможностью "Обновление устройства".</span><span class="sxs-lookup"><span data-stu-id="d1087-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="d1087-109">Вы можете добавить устройство проверки на страницу **Устройство проверки** и затем использовать его для проверки функциональных возможностей новых обновлений перед их развертыванием на производственных устройствах.</span><span class="sxs-lookup"><span data-stu-id="d1087-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="d1087-110">Вы можете протестировать устройство глобально (то есть в рамках всей среды) или для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="d1087-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="d1087-111">Устройство проверки указывается по MAC-адресу или серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="d1087-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="d1087-112">После добавления устройства оно появится в списке на странице " **тестирование устройства** " на панели управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="d1087-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d1087-113">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="d1087-113">Tasks you can perform</span></span>

<span data-ttu-id="d1087-114">На странице **Новое устройство проверки** или **Изменение устройства проверки** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d1087-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="d1087-115">добавить новое устройство проверки;</span><span class="sxs-lookup"><span data-stu-id="d1087-115">Add a new test device.</span></span>

- <span data-ttu-id="d1087-116">изменить свойства существующего устройства проверки.</span><span class="sxs-lookup"><span data-stu-id="d1087-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d1087-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="d1087-117">UI Reference</span></span>

<span data-ttu-id="d1087-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d1087-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d1087-119">**Область действия** Определяет область тестового устройства (глобально или на сайте).</span><span class="sxs-lookup"><span data-stu-id="d1087-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="d1087-120">**Name (имя** ) Вы можете добавить или изменить имя тестового устройства.</span><span class="sxs-lookup"><span data-stu-id="d1087-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="d1087-121">**Имя устройства** Вы можете добавить или изменить имя тестового устройства.</span><span class="sxs-lookup"><span data-stu-id="d1087-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="d1087-122">**Тип идентификатора** Вы можете выбрать метод, который будет использоваться для идентификации устройства, выбирая один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d1087-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="d1087-123">**MAC-адрес**</span><span class="sxs-lookup"><span data-stu-id="d1087-123">**MAC address**</span></span>

  - <span data-ttu-id="d1087-124">**Серийный номер**</span><span class="sxs-lookup"><span data-stu-id="d1087-124">**Serial number**</span></span>

- <span data-ttu-id="d1087-125">**Уникальный идентификатор** Вы можете ввести MAC-адрес или серийный номер устройства.</span><span class="sxs-lookup"><span data-stu-id="d1087-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="d1087-126">Дополнительные сведения о тестировании устройств см. в разделе [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="d1087-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="d1087-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d1087-127">See also</span></span>

[<span data-ttu-id="d1087-128">Тестовое устройство</span><span class="sxs-lookup"><span data-stu-id="d1087-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="d1087-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="d1087-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="d1087-130">Set-Кстестдевице</span><span class="sxs-lookup"><span data-stu-id="d1087-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="d1087-131">Просмотр обновлений программного обеспечения для устройств в Организации</span><span class="sxs-lookup"><span data-stu-id="d1087-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
