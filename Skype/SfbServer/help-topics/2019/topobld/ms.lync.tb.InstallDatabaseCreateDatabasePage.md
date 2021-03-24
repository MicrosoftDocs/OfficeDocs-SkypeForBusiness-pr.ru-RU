---
title: Установка и создание баз данных
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Можно выбрать базу данных, которую следует создать для используемого развертывания. По умолчанию база данных будет создаваться на определенном SQL Server определенном сайте и автоматически развертывать и настраивать файлы баз данных в зависимости от SQL Server, на который вы ставите базы данных.
ms.openlocfilehash: 160b42e510fc54b3f03375a0c86bc9f6bdf83f5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100055"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="43617-104">Установка и создание баз данных</span><span class="sxs-lookup"><span data-stu-id="43617-104">Install and Create Databases</span></span>

<span data-ttu-id="43617-105">Можно выбрать базу данных, которую следует создать для используемого развертывания.</span><span class="sxs-lookup"><span data-stu-id="43617-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="43617-106">По умолчанию база данных будет создаваться на определенном SQL Server определенном сайте и автоматически развертывать и настраивать файлы баз данных в зависимости от SQL Server, на который вы ставите базы данных.</span><span class="sxs-lookup"><span data-stu-id="43617-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="43617-p103">**Выберите базы данных, которые хотите создать**. Установите флажок напротив любой базы данных, которую следует развернуть и настроить. Установите флажок напротив тех баз данных, которые будут развернуты.</span><span class="sxs-lookup"><span data-stu-id="43617-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="43617-109">Необходимо SQL Server для экземпляра (если таково) и необходимо открыть порты брандмауэра для размещения экземпляра, в который развертываются базы данных.</span><span class="sxs-lookup"><span data-stu-id="43617-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="43617-110">Подробные сведения см. [в SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span><span class="sxs-lookup"><span data-stu-id="43617-110">For details, see [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span></span>

 <span data-ttu-id="43617-111">**Расширенный:** нажмите кнопку SQL Server кнопку **Advanced,** чтобы выбрать параметры расположения файлов базы данных на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43617-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="43617-112">Дополнительные сведения о размещении файлов с расширенными базами данных см. в материале Установка базы данных с помощью оболочки управления [Lync Server](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span><span class="sxs-lookup"><span data-stu-id="43617-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span></span>

 <span data-ttu-id="43617-113">**Назад**. Нажатие этой кнопки служит для перехода на предыдущий экран (иногда может быть недоступной в зависимости от способа перехода к этому диалоговому окну).</span><span class="sxs-lookup"><span data-stu-id="43617-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="43617-114">**Далее**. Нажатие этой кнопки фиксирует выбор в текущем диалоговом окне и позволяет перейти к следующему диалоговому окну для настройки дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="43617-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="43617-115">**Отмена.** Нажав эту кнопку, выйдите из конфигурации и откажитесь от изменений.</span><span class="sxs-lookup"><span data-stu-id="43617-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="43617-116">Некоторые, но не все экраны конфигурации подскажут вам, если вы хотите выйти и отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="43617-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="43617-117">Выбор **Да** закроет текущую конфигурацию и закроет текущую конфигурацию и возвращает вас в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="43617-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="43617-118">Выбор **"Нет"** возвращает вас в текущий диалоговое окно конфигурации и позволяет продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="43617-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="43617-119">**Справка**. Нажмите кнопку **Справка**, чтобы открыть справочные сведения, связанные с текущим диалоговым окном конфигурации.</span><span class="sxs-lookup"><span data-stu-id="43617-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>