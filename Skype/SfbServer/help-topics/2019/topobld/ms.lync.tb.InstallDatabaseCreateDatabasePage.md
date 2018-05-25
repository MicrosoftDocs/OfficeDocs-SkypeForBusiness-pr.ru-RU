---
title: Установка и создание баз данных
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Выберите базы данных, которые вы хотите создать для вашего развертывания. По умолчанию базы данных будут создаваться на определенном SQL Server на определенном сайте и автоматически развертывание и настройка файлов базы данных на SQL Server, размещении баз данных на основе.
ms.openlocfilehash: cf838e66dc5e9592ba71dd9d44fa5fc333c6dbc7
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="install-and-create-databases"></a><span data-ttu-id="d5db0-104">Установка и создание баз данных</span><span class="sxs-lookup"><span data-stu-id="d5db0-104">Install and Create Databases</span></span>
 
<span data-ttu-id="d5db0-105">Выберите базы данных, которые вы хотите создать для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="d5db0-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="d5db0-106">По умолчанию базы данных будут создаваться на определенном SQL Server на определенном сайте и автоматически развертывание и настройка файлов базы данных на SQL Server, размещении баз данных на основе.</span><span class="sxs-lookup"><span data-stu-id="d5db0-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="d5db0-107">**Выберите базы данных, которую вы хотите создать**: установите флажок все базы данных, которые планируется развернуть и настроить.</span><span class="sxs-lookup"><span data-stu-id="d5db0-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="d5db0-108">Установите флажок некоторых или всех баз данных, которые нужно развернуть.</span><span class="sxs-lookup"><span data-stu-id="d5db0-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d5db0-109">SQL Server должны уже настроены для экземпляра (если они имеются) и должны быть открыты порты брандмауэра для экземпляра, который развертывает администратор баз данных для учета.</span><span class="sxs-lookup"><span data-stu-id="d5db0-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="d5db0-110">Дополнительные сведения см [Настройка SQL Server для Lync Server 2013 Preview](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5db0-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="d5db0-111">**Дополнительно**: щелкните на сервере SQL Server и нажмите кнопку **Дополнительно** , чтобы выбрать расположения файлов на SQL Server для базы данных.</span><span class="sxs-lookup"><span data-stu-id="d5db0-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="d5db0-112">Сведения о размещение файлов базы данных в разделе [База данных установки с помощью консоли управления Lync Server](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5db0-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="d5db0-113">**Назад**: при нажатии этой кнопки возвращает к предыдущему (не всегда возможно, доступен, на основании как прибыли в этом диалоговом окне).</span><span class="sxs-lookup"><span data-stu-id="d5db0-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="d5db0-114">**Далее**: при нажатии этой кнопки фиксирует выбором, сделанным на текущее диалоговое окно и перейти к следующей диалоговое окно для настройки дополнительной информации</span><span class="sxs-lookup"><span data-stu-id="d5db0-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="d5db0-115">**Отмена**: при нажатии этой кнопки будет закройте конфигурацию и отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="d5db0-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="d5db0-116">Некоторые, но не все окна настроек выводит запрос, чтобы завершить работу и отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="d5db0-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="d5db0-117">Нажатие кнопки **Да** будет закрыть текущую конфигурацию и закрыть текущую конфигурацию и вы вернитесь к построителю топологий.</span><span class="sxs-lookup"><span data-stu-id="d5db0-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="d5db0-118">Выбор **No** можно вернуться в диалоговое окно текущей конфигурации и вы сможете продолжить конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d5db0-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="d5db0-119">**Справка**: при нажатии кнопки **Справка** отображается Эта справочная информация, связанного с текущей диалогового окна конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d5db0-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

