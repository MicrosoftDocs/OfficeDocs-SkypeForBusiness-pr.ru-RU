---
title: Установка и создание баз данных
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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Можно выбрать базу данных, которую следует создать для используемого развертывания. По умолчанию база данных будет создана на определенном SQL Server определенном сайте и будет автоматически развертывать и настраивать файлы баз данных в зависимости от SQL Server, в которой размещаются базы данных.
ms.openlocfilehash: 36912e468b0618925b3fbeb20db829d8d19249fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806939"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="92ab7-104">Установка и создание баз данных</span><span class="sxs-lookup"><span data-stu-id="92ab7-104">Install and Create Databases</span></span>

<span data-ttu-id="92ab7-105">Можно выбрать базу данных, которую следует создать для используемого развертывания.</span><span class="sxs-lookup"><span data-stu-id="92ab7-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="92ab7-106">По умолчанию база данных создается на определенном сайте SQL Server и автоматически развертывает и настраивает файлы баз данных на основе SQL Server, в которой размещаются базы данных.</span><span class="sxs-lookup"><span data-stu-id="92ab7-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="92ab7-p103">**Выберите базы данных, которые хотите создать**. Установите флажок напротив любой базы данных, которую следует развернуть и настроить. Установите флажок напротив тех баз данных, которые будут развернуты.</span><span class="sxs-lookup"><span data-stu-id="92ab7-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="92ab7-109">Для SQL Server уже должны быть настроены порты для экземпляра (если они есть), а для размещения экземпляра, в который развертываются базы данных, необходимо открыть порты брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="92ab7-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="92ab7-110">Подробные сведения см. в разделе [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="92ab7-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="92ab7-111">**Дополнительные.** Нажмите кнопку SQL Server кнопку "Дополнительные", чтобы выбрать параметры расположения файлов базы данных в SQL Server. </span><span class="sxs-lookup"><span data-stu-id="92ab7-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="92ab7-112">Дополнительные сведения о размещении файлов базы данных см. в руководстве по установке базы данных [с помощью Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="92ab7-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="92ab7-113">**Назад**. Нажатие этой кнопки служит для перехода на предыдущий экран (иногда может быть недоступной в зависимости от способа перехода к этому диалоговому окну).</span><span class="sxs-lookup"><span data-stu-id="92ab7-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="92ab7-114">**Далее**. Нажатие этой кнопки фиксирует выбор в текущем диалоговом окне и позволяет перейти к следующему диалоговому окну для настройки дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="92ab7-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="92ab7-115">**Отмена:** нажатие этой кнопки закимет конфигурацию и отменит изменения.</span><span class="sxs-lookup"><span data-stu-id="92ab7-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="92ab7-116">На некоторых, но не всех экранах конфигурации будет предложено выйти и отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="92ab7-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="92ab7-117">Если выбрать **"Да",** текущая конфигурация будет закрыта, а текущая конфигурация будет закрыта и возвращена в построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="92ab7-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="92ab7-118">Если выбрать **"Нет",** вы вернетесь в текущее диалоговое окно конфигурации и сможете продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="92ab7-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="92ab7-119">**Справка**. Нажмите кнопку **Справка**, чтобы открыть справочные сведения, связанные с текущим диалоговым окном конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92ab7-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


