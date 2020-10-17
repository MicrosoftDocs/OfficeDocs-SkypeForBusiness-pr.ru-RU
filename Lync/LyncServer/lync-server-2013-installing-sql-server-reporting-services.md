---
title: 'Lync Server 2013: Установка служб SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9044f90146b604f0277b0a5b815c6540849d58b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534936"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="d82fd-102">Установка служб SQL Server Reporting Services в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d82fd-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d82fd-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="d82fd-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="d82fd-104">Если вы планируете использовать Microsoft Lync Server 2013 Monitoring Reports (Дополнительные сведения см. в следующем разделе этой документации), необходимо сначала установить службы SQL Server Reporting Services; Службы Reporting Services можно устанавливать одновременно с установкой Microsoft SQL Server или в любое время после установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d82fd-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="d82fd-105">Если вы не установили SQL Server, следуйте инструкциям, приведенным выше в этой документации.</span><span class="sxs-lookup"><span data-stu-id="d82fd-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="d82fd-106">При установке SQL Server убедитесь, что на странице "Выбор компонентов" выбран пункт службы отчетов.</span><span class="sxs-lookup"><span data-stu-id="d82fd-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="d82fd-107">Будут установлены службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d82fd-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="d82fd-108">Если вы уже установили SQL Server, но не установили службы отчетов SQL Server, этот компонент можно добавить, используя при необходимости соответствующий набор инструкций для SQL Server 2008 R2 или SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d82fd-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="d82fd-109">Чтобы проверить, успешно ли установлены службы отчетов, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d82fd-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="d82fd-110">Если используется Microsoft SQL Server 2008 R2, в меню **Пуск** щелкните **Все программы**, выберите **Microsoft SQL Server 2008 R2**, щелкните **Средства конфигурирования** и выберите **Диспетчер конфигурации служб отчетов**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="d82fd-111">Если используется Microsoft SQL Server 2012, в меню **Пуск** щелкните **Все программы**, выберите **Microsoft SQL Server 2012**, щелкните **Средства конфигурирования** и выберите **Диспетчер конфигурации служб отчетов**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="d82fd-p102">В диалоговом окне **Подключение конфигурации служб отчетов** убедитесь, что имя вашего сервера отображается в поле **Имя сервера** и что имя экземпляра SQL Server, в котором хранятся данные мониторинга, отображается в поле **Экземпляр сервера отчетов**. Нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="d82fd-114">В диспетчере конфигурации служб отчетов на панели состояния сервера отчетов должна отображаться, что установлены службы SQL Server Reporting Services и службы отчетов в настоящее время: состояние сервера отчетов должно отображаться как **запущенное** , а кнопка " **Пуск** " должна быть серым и недоступна.</span><span class="sxs-lookup"><span data-stu-id="d82fd-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="d82fd-115">Если службы отчетов не запущены, нажмите кнопку **Пуск**, чтобы запустить их.</span><span class="sxs-lookup"><span data-stu-id="d82fd-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="d82fd-116">Если база данных не отображается рядом с меткой "Имя базы данных сервера отчетов", выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d82fd-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="d82fd-117">В диспетчере конфигурации служб отчетов щелкните **База данных**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="d82fd-118">В области базы данных сервера отчетов выберите **Изменить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="d82fd-119">В мастере настройки базы данных сервера отчетов в области действий выберите параметр **Создать базу данных сервера отчетов**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="d82fd-p104">В мастере настройки базы данных сервера отчетов в области сервера баз данных убедитесь, что в полях **Имя сервера**, **Тип проверки подлинности** и **Имя пользователя** указаны правильные сведения. Нажмите кнопку **Проверить подключение**, чтобы проверить связь с сервером базы данных, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="d82fd-122">В мастере настройки базы данных сервера отчетов в области базы данных примите значения по умолчанию для параметров **Имя базы данных**, \*\*Язык \*\* и **Режим сервера отчетов**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="d82fd-123">В мастере настройки базы данных сервера отчетов в области учетных данных убедитесь, что в раскрывающемся списке **Тип проверки подлинности** и полях **Имя пользователя** и **Пароль** указаны правильные данные, а затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="d82fd-124">В мастере настройки базы данных сервера отчетов в области сводки нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="d82fd-125">В мастере настройки базы данных сервера отчетов в области "Ход выполнения и завершение" нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d82fd-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="d82fd-p105">Чтобы проверить, настроены ли URL-адреса службы отчетов, щелкните **URL-адрес веб-службы**. Вы должны увидеть один или несколько URL-адресов, перечисленных под заголовком \*\*URL-адреса веб-службы сервера отчетов \*\*. Щелкните каждую из этих ссылок, чтобы убедиться, что вы можете открыть домашнюю страницу для локальной установки служб отчетов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d82fd-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

