---
title: 'Lync Server 2013: использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="60ea9-102">Использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ea9-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60ea9-103">_**Тема последнего изменения:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="60ea9-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="60ea9-104">Чтобы использовать в качестве серверной части базу данных SQL Server 2008 R2, выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="60ea9-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="60ea9-105">Настройка SQL Server 2008 R2 и служб SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="60ea9-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="60ea9-106">Прежде чем приступить к установке System Center Operations Manager, вы должны внести два изменения в сервер SQL Server 2008 R2 и настройку служб SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="60ea9-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="60ea9-107">(Эти изменения необходимы только в том случае, если в качестве базы данных Operations Manager используется SQL Server 2008 R2). Для начала сделайте следующее на компьютере, на котором будет размещена база данных Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="60ea9-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="60ea9-108">Нажмите кнопку **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="60ea9-109">В диалоговом окне **выполнить** введите **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50. арчинст\\Reporting\\Services ReportServer** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="60ea9-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="60ea9-110">В папке **ReportServer** откройте файл **RSReportServer. config** в блокноте или любом другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="60ea9-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="60ea9-111">В начале файла будет показан ряд узлов "добавить ключ".</span><span class="sxs-lookup"><span data-stu-id="60ea9-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="60ea9-112">Найдите запись, которая начинается \*\* \<с ключевого слова Add = "секуреконнектионлевел"\*\* , и установите для параметра значение **0**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="60ea9-113">Сохраните файл **RSReportServer. config** и закройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="60ea9-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="60ea9-114">После обновления файла конфигурации сервера отчетов необходимо назначить для служб SQL Server Reporting Services правильный сертификат.</span><span class="sxs-lookup"><span data-stu-id="60ea9-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="60ea9-115">Для этого:</span><span class="sxs-lookup"><span data-stu-id="60ea9-115">To do that:</span></span>

1.  <span data-ttu-id="60ea9-116">Нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft SQL Server 2008 R2**, выберите пункт **средства настройки**, а затем — **Диспетчер конфигурации служб Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="60ea9-117">В диалоговом окне **Подключение к конфигурации служб Reporting Services** убедитесь в том, что имя сервера отображается в поле **имя сервера** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="60ea9-118">Выберите экземпляр SQL Server, на котором будет размещена база данных Operations Manager (например, **арчинст**), из раскрывающегося списка **экземпляр сервера отчетов** и нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="60ea9-119">В диспетчере конфигураций служб Reporting Services щелкните **URL-адрес Web Service**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="60ea9-120">На странице **URL веб-служба** выберите сертификат, который будет использоваться в службах отчетов в раскрывающемся списке **сертификата SSL** , и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="60ea9-121">Через несколько секунд вы увидите пару URL-адресов, которые указаны в разделе **URL — ссылки на службы сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="60ea9-122">Щелкните оба URL-адреса, чтобы убедиться, что у вас есть доступ к службам SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="60ea9-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="60ea9-123">Закройте Диспетчер конфигураций служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="60ea9-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="60ea9-124">Создание базы данных System Center Operations Manager для использования с SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="60ea9-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="60ea9-125">Если вы хотите настроить System Center Operations Manager на использование базы данных SQL Server 2008 R2, вам потребуется выполнить вручную создание базы данных Operations Manager на компьютере с SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="60ea9-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="60ea9-126">(Опять же, эти действия не требуются, если в качестве серверной базы данных используется SQL Server 2005 или SQL Server 2008.)</span><span class="sxs-lookup"><span data-stu-id="60ea9-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="60ea9-127">Чтобы вручную создать базу данных Operations Manager, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="60ea9-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="60ea9-128">На странице System Center Operations Manager 2007 R2 с помощью установочного носителя\\в папке суппорттулс AMD64 дважды щелкните **дбкреатевизард. exe**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="60ea9-129">В мастере настройки базы данных на странице **Добро пожаловать в мастер настройки базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="60ea9-130">На странице **сведения о базе данных** оставьте все параметры как есть и нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="60ea9-131">На странице **Конфигурация группы управления** введите имя группы управления (например, " **наблюдение за Lync Server**") в поле **имя группы управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="60ea9-132">На странице " **отчеты об ошибках Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="60ea9-133">На странице **Сводка** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="60ea9-134">Создание хранилища данных System Center Operations Manager для использования с SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="60ea9-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="60ea9-135">Microsoft Lync Server 2013 поставляется с тремя новыми отчетами System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="60ea9-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="60ea9-136">**Отчет о доступности сценария «завершить**   » в этом отчете подробно описана доступность и время работы для основных служб Lync Server, таких как регистрация или присутствие.</span><span class="sxs-lookup"><span data-stu-id="60ea9-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="60ea9-137">**Отчет о емкости**   с использованием данных счетчиков производительности этот отчет показывает тенденции для системных компонентов, таких как доступность памяти и использование процессора.</span><span class="sxs-lookup"><span data-stu-id="60ea9-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="60ea9-138">**Отчет о**   компоненте в этом отчете перечислены Топ генераторов оповещений, сгруппированных по компоненту Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60ea9-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="60ea9-139">Для использования этих новых отчетов необходимо установить хранилище данных System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="60ea9-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="60ea9-140">(Хранилище данных обеспечивает долгосрочное хранение данных операций.) Для использования хранилища данных с SQL Server 2008 R2 необходимо выполнить следующие действия на компьютере, на котором размещается база данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60ea9-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="60ea9-141">На носителе с программой установки System Center Operations Manager в папке\\Setup\\Суппорттулс AMD64 дважды щелкните **дбкреатевизард. exe**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="60ea9-142">В мастере настройки базы данных на странице **Добро пожаловать в мастер настройки базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="60ea9-143">На странице **сведения о базе данных** выберите **базу данных хранилища данных Operations Manager** из раскрывающегося списка **тип базы данных** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="60ea9-144">На странице **Сводка** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="60ea9-145">Установка консоли System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="60ea9-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="60ea9-146">Консоль Operations Manager — это основное средство, используемое для управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="60ea9-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="60ea9-147">Перед установкой консоли Operations Manager убедитесь в том, что вы установили поддерживаемую версию SQL Server и службу SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="60ea9-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="60ea9-148">Кроме того, для проверки правильности установки и настройки службы отчетов рекомендуется запустить диспетчер конфигурации служб отчетов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60ea9-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="60ea9-149">Чтобы установить консоль System Center Operations Manager, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="60ea9-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="60ea9-150">На носителе с программой установки System Center Operations Manager дважды щелкните **сетупом. exe**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="60ea9-151">В программе System Center Operations Manager 2007 R2 нажмите кнопку **проверить необходимые компоненты**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="60ea9-152">В средстве просмотра требований System Center Operations Manager выберите компоненты System Center, которые необходимо установить: (**сервер**; **Консоль**; и **PowerShell**), а затем нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="60ea9-153">Убедитесь, что блокирующие проблемы не обнаружены, и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="60ea9-154">Если была обнаружена проблема с блокировкой, исправьте ее и нажмите кнопку **проверить** , чтобы повторно запустить проверку готовности.</span><span class="sxs-lookup"><span data-stu-id="60ea9-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="60ea9-155">В программе System Center Operations Manager нажмите кнопку **установить Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="60ea9-156">В мастере настройки System Center Operations Manager на странице **Добро пожаловать на страницу мастера установки System Center Operations Manager** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="60ea9-157">На странице **лицензионного соглашения для конечных пользователей** выберите **я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="60ea9-158">На странице **Регистрация продукта** введите свое имя в поле **имя пользователя** и имя Организации в поле **Организация** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="60ea9-159">Введите ключ продукта System Center Operations Manager в поле **введите 25-значный ключ** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="60ea9-160">На странице **Выборочная установка** выберите параметры System Center, которые нужно установить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="60ea9-161">Необходимо выбрать **сервер управления**, **пользовательские интерфейсы**и **веб-консоль** для установки.</span><span class="sxs-lookup"><span data-stu-id="60ea9-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="60ea9-162">**Базу данных** не следует выделять и не нужно устанавливать.</span><span class="sxs-lookup"><span data-stu-id="60ea9-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="60ea9-163">На странице **экземпляр сервера базы данных SC** убедитесь в том, что имя компьютера, на котором установлены базы данных Operations Manager, отображается в поле **сервер System Center Database Server** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="60ea9-164">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-164">Click **Next**.</span></span>

10. <span data-ttu-id="60ea9-165">На странице **учетной записи действия сервера управления** выберите **Доменная или локальная учетная запись компьютера** , а затем введите нужные значения в поля **учетная запись пользователя**, **пароль**, **домен или локальный компьютер** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="60ea9-166">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-166">Click **Next**.</span></span>

11. <span data-ttu-id="60ea9-167">На странице **SDK и учетной записи службы настройки** выберите **Доменная или локальная учетная запись компьютера** , а затем введите нужные значения в поля **учетная запись пользователя**, **пароль**, **домен или локальный компьютер** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="60ea9-168">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-168">Click **Next**.</span></span>

12. <span data-ttu-id="60ea9-169">На странице " **отчеты об ошибках Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="60ea9-170">На странице **программы улучшения качества программного** обеспечения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="60ea9-171">На странице **готовность к установке программы** нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="60ea9-172">На странице **Завершение установки System Center Operations Manager** снимите флажок **резервное копирование ключа шифрования** и установите **флажки для консоли** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="60ea9-173">В программе System Center Operations Manager щелкните **выход**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="60ea9-174">Установка служб отчетов System Center</span><span class="sxs-lookup"><span data-stu-id="60ea9-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="60ea9-175">После установки и настройки консоли System Center Operations Manager необходимо установить System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="60ea9-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="60ea9-176">Если в качестве серверной базы данных Operations Manager используется SQL Server 2008 R2, это означает, что вы должны сначала внести временное изменение в группу безопасности, связанную со службами SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="60ea9-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="60ea9-177">Если вы используете SQL Server 2008 R2, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="60ea9-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="60ea9-178">Нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="60ea9-179">В диспетчере серверов разверните узел **Конфигурация**, разверните раздел **Локальные пользователи и группы**, а затем выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="60ea9-180">Найдите следующую группу, в которой ATL-SC-001 представляет имя вашего компьютера и АРЧИНСТ представляет экземпляр SQL Server для базы данных System Center: **склсерверрепортсерверусер $ ATL-SC-001 $ MSRS10\_50. арчинст**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="60ea9-181">Щелкните группу правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="60ea9-182">Переименуйте группу, удалив \*\* \_50\*\* из имени группы.</span><span class="sxs-lookup"><span data-stu-id="60ea9-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="60ea9-183">Например: **склсерверрепортсерверусер $ ATL-SC-001 $ MSRS10. АРЧИНСТ**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="60ea9-184">Закройте Диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="60ea9-184">Close Server Manager.</span></span>

<span data-ttu-id="60ea9-185">На этом этапе вы можете установить службы отчетов System Center.</span><span class="sxs-lookup"><span data-stu-id="60ea9-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="60ea9-186">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="60ea9-186">To do this:</span></span>

1.  <span data-ttu-id="60ea9-187">На диске System Center Operations Manager 2007 R2 дважды щелкните **сетупом. exe**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="60ea9-188">В программе System Center Operations Manager 2007 R2 щелкните **установить Отчеты Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="60ea9-189">В мастере настройки отчетов System Center Operations Manager 2007 R2 на странице **Добро пожаловать в отчеты Operations Manager Настройка** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="60ea9-190">На странице **лицензионного соглашения для конечных пользователей** установите флажок **я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="60ea9-191">На странице **Регистрация продукта** убедитесь, что имя и имя вашей организации указаны в полях **имя пользователя** и **Организация** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="60ea9-192">На странице **Выборочная настройка** выберите пункт **сервер отчетов** , а затем — **этот компонент и все зависимые компоненты будут установлены на локальном жестком**диске.</span><span class="sxs-lookup"><span data-stu-id="60ea9-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="60ea9-193">Нажмите кнопку **хранилище данных** и выберите **этот компонент будет недоступен**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="60ea9-194">На странице **Подключение к корневому серверу управления** введите имя корневого сервера управления Operations Manager в поле **корневой сервер управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="60ea9-195">На странице **Подключение к хранилищу данных Operations Manager** введите экземпляр SQL Server, на котором находится хранилище данных, в поле **экземпляр SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="60ea9-196">(Если хранилище данных находится в экземпляре по умолчанию, просто введите имя сервера, например ATL-SQL-001.) Убедитесь в том, что имя базы данных **оператионсманажердв** отображается в поле **имя** , а этот порт **1433** отображается в поле Port ( **порт) сервера SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="60ea9-197">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-197">Click **Next**.</span></span>

9.  <span data-ttu-id="60ea9-198">На странице **экземпляра SQL Server Reporting** выберите сервер отчетов SQL Server из раскрывающегося списка **введите сервер служб SQL Server Reporting Services** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="60ea9-199">На странице запись **учетной записи хранилища данных** введите имя и пароль пользователя, которому должны быть первоначально назначены разрешения на запись в хранилище данных в полях **учетная запись пользователя** и **пароль** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="60ea9-200">Выберите домен пользователя из раскрывающегося списка **домен** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="60ea9-201">На странице **учетной записи средства чтения данных** введите имя и пароль учетной записи пользователя, которая будет использоваться при запросе службами SQL Reporting Services хранилища данных в полях **учетной записи пользователя** и **пароля** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="60ea9-202">Выберите домен учетной записи из раскрывающегося списка **домена** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="60ea9-203">На странице **оперативные отчеты данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="60ea9-204">На странице **центра обновления Майкрософт** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="60ea9-205">На странице **готовность к установке программы** нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="60ea9-206">На странице **Завершение работы мастера настройки компонентов отчетов Operations Manager** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="60ea9-207">В программе System Center Operations Manager 2007 R2 нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="60ea9-208">После установки System Center Reporting вы можете сбросить имя группы безопасности, связанной с отчетом SQL Server, с помощью описанной ниже процедуры.</span><span class="sxs-lookup"><span data-stu-id="60ea9-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="60ea9-209">Эта процедура может потребоваться, только если вы используете SQL Server:</span><span class="sxs-lookup"><span data-stu-id="60ea9-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="60ea9-210">Нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="60ea9-211">В диспетчере серверов разверните узел **Конфигурация**, разверните раздел **Локальные пользователи и группы**, а затем выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="60ea9-212">Найдите следующую группу, в которой ATL-SC-001 представляет имя вашего компьютера и АРЧИНСТ представляет экземпляр SQL Server для баз данных архивации и мониторинга: **склсерверрепортсерверусер $ ATL-SC-001 $ MSRS10. АРЧИНСТ**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="60ea9-213">Щелкните группу правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="60ea9-214">Переименуйте группу, добавив \*\* \_50\*\* в конец имени группы, прямо перед именем экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60ea9-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="60ea9-215">Например: **склсерверрепортсерверусер $ ATL-SC-001 $ MSRS10\_50. арчинст**.</span><span class="sxs-lookup"><span data-stu-id="60ea9-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="60ea9-216">Закройте Диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="60ea9-216">Close Server Manager.</span></span>

<span data-ttu-id="60ea9-217">Если открыта консоль Operations Center, необходимо закрыть приложение, а затем перезапустить его. Если этого не сделать, вкладка " **отчеты** " не появится в пользовательском интерфейсе консоли операций.</span><span class="sxs-lookup"><span data-stu-id="60ea9-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="60ea9-218">Обратите внимание, что после первого запуска консоли операций может пройти несколько минут, прежде чем все отчеты наблюдения будут отображены на вкладке **отчеты** .</span><span class="sxs-lookup"><span data-stu-id="60ea9-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

