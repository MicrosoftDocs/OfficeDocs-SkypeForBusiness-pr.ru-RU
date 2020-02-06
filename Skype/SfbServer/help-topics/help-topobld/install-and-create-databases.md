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
- NOCSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Вы выбираете базы данных, которые вы хотите создать для развертывания. По умолчанию база данных будет создана на сервере SQL Server, определенном в определенном сайте, и будет автоматически развертываться и настраиваться для файлов базы данных на основе сервера SQL Server, на котором вы размещаете базы данных.
ms.openlocfilehash: 72eebc4523eb538762adcfd3c2ee7138853a80ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819831"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="57748-104">Установка и создание баз данных</span><span class="sxs-lookup"><span data-stu-id="57748-104">Install and Create Databases</span></span>

<span data-ttu-id="57748-105">Вы выбираете базы данных, которые вы хотите создать для развертывания.</span><span class="sxs-lookup"><span data-stu-id="57748-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="57748-106">По умолчанию база данных будет создана на сервере SQL Server, определенном в определенном сайте, и будет автоматически развертываться и настраиваться для файлов базы данных на основе сервера SQL Server, на котором вы размещаете базы данных.</span><span class="sxs-lookup"><span data-stu-id="57748-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="57748-107">**Выберите базы данных, которые вы хотите создать**: установите флажки для всех баз данных, которые вы хотите развернуть и настроить.</span><span class="sxs-lookup"><span data-stu-id="57748-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="57748-108">Установите флажки для всех баз данных, которые вы развернете.</span><span class="sxs-lookup"><span data-stu-id="57748-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="57748-109">Сервер SQL Server должен быть уже настроен для экземпляра (если есть), а порты брандмауэра должны быть открыты для размещения экземпляра, на который развертываются базы данных.</span><span class="sxs-lookup"><span data-stu-id="57748-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="57748-110">Дополнительные сведения можно найти в разделе [Настройка SQL Server для Lync server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="57748-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="57748-111">**Дополнительно**: щелкните SQL Server и нажмите кнопку " **Дополнительно** ", чтобы выбрать параметры расположения файла базы данных на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="57748-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="57748-112">Дополнительные сведения о размещении файлов баз данных см. в разделе [Установка баз данных с помощью командной консоли Lync Server](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="57748-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="57748-113">**Назад**: при нажатии этой кнопки вы вернетесь к предыдущему экрану (в зависимости от того, как вы попали в этом диалоговом окне), это может быть недоступно.</span><span class="sxs-lookup"><span data-stu-id="57748-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="57748-114">**Далее**: нажмите эту кнопку, чтобы подтвердить выбор в текущем диалоговом окне и перейти к следующему диалоговому окну для настройки дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="57748-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="57748-115">**Отмена**: нажатие этой кнопки приведет к закрытию конфигурации и отмене изменений.</span><span class="sxs-lookup"><span data-stu-id="57748-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="57748-116">Некоторые, но не все экраны конфигурации выводят приглашение, если вы захотите закрыть и отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="57748-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="57748-117">Нажмите **кнопку Да** , чтобы закрыть текущую конфигурацию и закрыть текущую конфигурацию и вернуться к построителю топологии.</span><span class="sxs-lookup"><span data-stu-id="57748-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="57748-118">Если нажать кнопку **нет** , откроется диалоговое окно текущее настройки и вы сможете продолжить настройку.</span><span class="sxs-lookup"><span data-stu-id="57748-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="57748-119">**Справка**: нажатие кнопки " **Справка** " приводит к отображению этой справочной информации, связанной с текущим диалоговым окном настройки.</span><span class="sxs-lookup"><span data-stu-id="57748-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


