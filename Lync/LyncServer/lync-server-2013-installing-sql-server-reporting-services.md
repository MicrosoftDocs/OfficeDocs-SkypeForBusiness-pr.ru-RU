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
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="70d0c-102">Установка служб SQL Server Reporting Services в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d0c-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70d0c-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="70d0c-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="70d0c-104">Если вы планируете использовать Microsoft Lync Server 2013 для мониторинга отчетов (Дополнительные сведения можно найти в следующем разделе этой документации), необходимо сначала установить службы отчетов SQL Server; Службы Reporting Services могут быть установлены одновременно с установкой Microsoft SQL Server или в любое время после установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70d0c-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="70d0c-105">Если вы не установили SQL Server, следуйте инструкциям, приведенным выше в этой документации.</span><span class="sxs-lookup"><span data-stu-id="70d0c-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="70d0c-106">При установке SQL Server убедитесь, что на странице выбора функций вы выбрали пункт службы отчетов.</span><span class="sxs-lookup"><span data-stu-id="70d0c-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="70d0c-107">Будут установлены службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="70d0c-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="70d0c-108">Если вы уже установили SQL Server, но не установили службы SQL Server Reporting Services, вы можете добавить эту функцию, следуя указаниям по соответствующему набору инструкций для SQL Server 2008 R2 или SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="70d0c-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="70d0c-109">Чтобы убедиться в том, что службы Reporting Services успешно установлены, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="70d0c-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="70d0c-110">Если вы используете Microsoft SQL Server 2008 R2, нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft SQL Server 2008 R2**, выберите пункт **средства настройки**, а затем — **Диспетчер конфигурации служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="70d0c-111">Если вы используете Microsoft SQL Server 2012, нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft SQL Server 2012**, выберите пункт **средства настройки**, а затем — **Диспетчер конфигурации служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="70d0c-112">В диалоговом окне **Подключение к конфигурации служб Reporting Services** убедитесь в том, что имя сервера отображается в поле **имя сервера** , и что имя экземпляра SQL Server, в котором хранятся данные мониторинга, отображается в поле **экземпляр сервера отчетов** .</span><span class="sxs-lookup"><span data-stu-id="70d0c-112">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="70d0c-113">Нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-113">Click **Connect**.</span></span>

<span data-ttu-id="70d0c-114">В диспетчере конфигураций служб отчетов на панели состояния сервера отчетов должна быть указана установка служб SQL Server Reporting Services и использование служб отчетов: состояние сервера отчетов должно отображаться как **запущенное** , а кнопка " **Пуск** " — в недоступном состоянии.</span><span class="sxs-lookup"><span data-stu-id="70d0c-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="70d0c-115">Если служба отчетов не запущена, нажмите кнопку **начать** , чтобы запустить ее.</span><span class="sxs-lookup"><span data-stu-id="70d0c-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="70d0c-116">Если база данных не указана рядом с меткой имя базы данных сервера отчетов, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="70d0c-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="70d0c-117">В диспетчере конфигураций служб Reporting Services щелкните **база данных**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="70d0c-118">В области базы данных сервера отчетов нажмите кнопку **изменить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="70d0c-119">В мастере настройки базы данных сервера отчетов на панели действий выберите **создать новую базу данных сервера отчетов** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="70d0c-120">В мастере настройки базы данных сервера отчетов на панели "сервер базы данных" убедитесь, что данные указаны правильно в полях **имя сервера**, **тип проверки подлинности**и **имя пользователя** .</span><span class="sxs-lookup"><span data-stu-id="70d0c-120">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="70d0c-121">Нажмите кнопку **проверить подключение** , чтобы проверить, можно ли установить соединение с сервером базы данных, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-121">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="70d0c-122">В мастере настройки базы данных сервера отчетов в области базы данных подтвердите значения по умолчанию для **имени базы данных**, **языка**и **сервера отчетов** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="70d0c-123">В мастере настройки базы данных сервера отчетов на панели учетные данные убедитесь в том, что в раскрывающемся списке **тип проверки подлинности** указаны **нужные** сведения \*\*\*\* , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="70d0c-124">В мастере настройки базы данных сервера отчетов в области Сводка нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="70d0c-125">В мастере настройки базы данных сервера отчетов в области ход выполнения и завершения нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="70d0c-126">Чтобы проверить, правильно ли настроены URL-адреса служб отчетов, выберите пункт URL — этот **адрес**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-126">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="70d0c-127">Вы должны увидеть один или несколько URL-адресов, указанных в списке под заголовком **URL — адрес веб службы сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="70d0c-127">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="70d0c-128">Щелкните каждый из этих URL-адресов, чтобы убедиться, что вы можете попасть на домашнюю страницу локальной установки служб SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="70d0c-128">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

