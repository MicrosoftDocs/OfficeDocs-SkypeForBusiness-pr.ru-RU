---
title: Установка и создание баз данных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Можно выбрать базу данных, которую следует создать для используемого развертывания. По умолчанию база данных будет создана на определенном сайте SQL Server, а файлы базы данных будут автоматически развернуты и настроены на основе SQL Server, на котором размещаются базы данных.
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215390"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="9490e-104">Установка и создание баз данных</span><span class="sxs-lookup"><span data-stu-id="9490e-104">Install and Create Databases</span></span>

<span data-ttu-id="9490e-105">Можно выбрать базу данных, которую следует создать для используемого развертывания.</span><span class="sxs-lookup"><span data-stu-id="9490e-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="9490e-106">По умолчанию база данных будет создана на определенном сайте SQL Server, а файлы базы данных будут автоматически развернуты и настроены на основе SQL Server, на котором размещаются базы данных.</span><span class="sxs-lookup"><span data-stu-id="9490e-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="9490e-p103">**Выберите базы данных, которые хотите создать**. Установите флажок напротив любой базы данных, которую следует развернуть и настроить. Установите флажок напротив тех баз данных, которые будут развернуты.</span><span class="sxs-lookup"><span data-stu-id="9490e-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="9490e-109">SQL Server должен быть уже настроен для экземпляра (если он есть), а порты брандмауэра должны быть открыты для размещения экземпляра, в котором развертываются базы данных.</span><span class="sxs-lookup"><span data-stu-id="9490e-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="9490e-110">Подробные сведения см. в разделе [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="9490e-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="9490e-111">**Дополнительно**: щелкните SQL Server и нажмите кнопку **Дополнительно** , чтобы выбрать параметры для расположений файлов базы данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9490e-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="9490e-112">Дополнительные сведения о размещении файлов баз данных можно найти в статье [Установка баз данных с помощью Командная консоль Lync Server](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="9490e-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="9490e-113">**Назад**. Нажатие этой кнопки служит для перехода на предыдущий экран (иногда может быть недоступной в зависимости от способа перехода к этому диалоговому окну).</span><span class="sxs-lookup"><span data-stu-id="9490e-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="9490e-114">**Далее**. Нажатие этой кнопки фиксирует выбор в текущем диалоговом окне и позволяет перейти к следующему диалоговому окну для настройки дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="9490e-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="9490e-115">**Отмена**: нажатие этой кнопки приведет к выходу из конфигурации и отмене изменений.</span><span class="sxs-lookup"><span data-stu-id="9490e-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="9490e-116">Некоторые, но не все экраны конфигурации, запрашивают вас, если вы хотите выйти и отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="9490e-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="9490e-117">При выборе значения **"Да"** закрывается текущая конфигурация и закрывается текущая конфигурация и возвращается построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="9490e-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="9490e-118">Если нажать кнопку **нет** , откроется диалоговое окно текущей конфигурации и вы сможете продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="9490e-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="9490e-119">**Справка**. Нажмите кнопку **Справка**, чтобы открыть справочные сведения, связанные с текущим диалоговым окном конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9490e-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


