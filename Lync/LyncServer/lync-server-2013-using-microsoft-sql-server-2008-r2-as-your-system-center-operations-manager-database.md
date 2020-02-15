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
ms.openlocfilehash: 6ad7854043eb85db7b5d260d57beed26746160f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="7661a-102">Использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7661a-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7661a-103">_**Последнее изменение темы:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="7661a-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="7661a-104">Чтобы использовать SQL Server 2008 R2 в качестве серверной базы данных, выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7661a-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="7661a-105">Настройка SQL Server 2008 R2 и SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7661a-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="7661a-106">Прежде чем приступить к установке System Center Operations Manager, необходимо внести два изменения в конфигурацию SQL Server 2008 R2 и службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="7661a-107">(Эти изменения необходимы только в том случае, если в качестве базы данных Operations Manager используется SQL Server 2008 R2). Сначала выполните следующие действия на компьютере, на котором будет размещаться база данных Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="7661a-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="7661a-108">В меню **Пуск** щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7661a-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="7661a-109">В диалоговом окне **выполнить** введите **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50. ARCHINST\\Reporting\\Services ReportServer** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7661a-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="7661a-110">В папке **ReportServer** откройте файл **RSReportServer. config** в блокноте или любом другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="7661a-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="7661a-111">В начале файла отображается ряд узлов "Добавление ключа".</span><span class="sxs-lookup"><span data-stu-id="7661a-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="7661a-112">Найдите запись, которая начинает \*\* \<добавлять ключ = "секуреконнектионлевел"\*\* , и присвойте этому параметру значение **0**:</span><span class="sxs-lookup"><span data-stu-id="7661a-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="7661a-113">Сохраните файл **RSReportServer. config** и закройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="7661a-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="7661a-114">После обновления файла конфигурации сервера отчетов необходимо назначить правильный сертификат службам отчетов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7661a-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="7661a-115">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7661a-115">To do that:</span></span>

1.  <span data-ttu-id="7661a-116">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft SQL Server 2008 R2**и **средства настройки**, а затем щелкните **Диспетчер конфигураций Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="7661a-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="7661a-117">В диалоговом окне **Подключение к конфигурации служб Reporting Services** убедитесь, что имя сервера отображается в поле **имя сервера** .</span><span class="sxs-lookup"><span data-stu-id="7661a-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="7661a-118">Выберите экземпляр SQL Server, на котором будет размещаться база данных Operations Manager (например, **ARCHINST**), из раскрывающегося списка **экземпляр сервера отчетов** и нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="7661a-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="7661a-119">В диспетчере конфигурации служб Reporting Services щелкните **URL-адрес веб-службы**.</span><span class="sxs-lookup"><span data-stu-id="7661a-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="7661a-120">На странице **URL-адрес веб-службы** выберите сертификат, который будет использоваться для служб отчетов, в раскрывающемся списке **SSL-сертификат** , а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="7661a-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="7661a-121">Через несколько секунд вы увидите пару URL-адресов, перечисленных в разделе **URL-адреса веб-службы сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="7661a-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="7661a-122">Щелкните оба URL-адреса, чтобы убедиться, что вы можете получить доступ к службам SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="7661a-123">Закройте Диспетчер конфигураций служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="7661a-124">Создание базы данных System Center Operations Manager для использования с SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7661a-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="7661a-125">Если вы хотите настроить System Center Operations Manager для использования базы данных SQL Server 2008 R2, необходимо создать базу данных Operations Manager на компьютере с SQL Server 2008 R2, выполнив команду "вручную".</span><span class="sxs-lookup"><span data-stu-id="7661a-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="7661a-126">(Опять же, эти действия не требуются, если вы используете SQL Server 2005 или SQL Server 2008 в качестве внутренней базы данных.)</span><span class="sxs-lookup"><span data-stu-id="7661a-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="7661a-127">Чтобы вручную создать базу данных Operations Manager, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7661a-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="7661a-128">На установочном носителе System Center Operations Manager 2007 R2 в папке Суппорттулс\\AMD64 дважды щелкните файл **исполняемый файл dbcreatewizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="7661a-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="7661a-129">В мастере настройки базы данных на странице **Добро пожаловать в мастер настройки базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="7661a-130">На странице **сведения о базе данных** оставьте все параметры как есть, а затем нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="7661a-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="7661a-131">На странице " **Конфигурация группы управления** " введите имя группы управления (например, " **наблюдение за Lync Server**") в поле **имя группы управления** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="7661a-132">На странице " **отчеты об ошибках Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="7661a-133">На странице **Сводка** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7661a-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="7661a-134">Создание хранилища данных System Center Operations Manager для использования с SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7661a-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="7661a-135">В состав Microsoft Lync Server 2013 входит три новых отчета System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="7661a-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="7661a-136">**Отчет о доступности сценария**   "до конца" в этом отчете подробно описывается доступность и время работы для ключевых служб Lync Server, таких как регистрация или присутствие.</span><span class="sxs-lookup"><span data-stu-id="7661a-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="7661a-137">**Отчет о емкости**   с использованием данных счетчиков производительности этот отчет показывает тенденции для компонентов системы, таких как доступность памяти и загрузка процессора.</span><span class="sxs-lookup"><span data-stu-id="7661a-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="7661a-138">**Отчет о**   компонентах в этом отчете перечислены Топ генераторов оповещений, сгруппированных по компонентам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7661a-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="7661a-139">Чтобы использовать эти новые отчеты, необходимо установить хранилище данных System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="7661a-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="7661a-140">(Хранилище данных обеспечивает долговременное хранение данных операций.) Чтобы использовать хранилище данных с SQL Server 2008 R2, выполните следующие действия на компьютере, на котором размещается база данных SQL Server:</span><span class="sxs-lookup"><span data-stu-id="7661a-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="7661a-141">На установочном носителе System Center Operations Manager в папке Setup\\суппорттулс\\AMD64 дважды щелкните файл **исполняемый файл dbcreatewizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="7661a-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="7661a-142">В мастере настройки базы данных на странице **Добро пожаловать в мастер настройки базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="7661a-143">На странице **сведения о базе данных** выберите **базу данных хранилища данных Operations Manager** в раскрывающемся списке **тип базы данных** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="7661a-144">На странице **Сводка** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7661a-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="7661a-145">Установка консоли System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="7661a-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="7661a-146">Консоль Operations Manager — это основное средство, используемое для управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="7661a-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="7661a-147">Перед установкой консоли Operations Manager убедитесь, что установлена поддерживаемая версия SQL Server и служба SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="7661a-148">Также рекомендуется запустить диспетчер конфигурации служб отчетов SQL Server, чтобы убедиться, что служба Reporting Services установлена и настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="7661a-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="7661a-149">Установка консоли System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="7661a-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="7661a-150">На носителе программы установки System Center Operations Manager дважды щелкните **исполняемый файл SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="7661a-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="7661a-151">В программе установки System Center Operations Manager 2007 R2 щелкните **проверить предварительные требования**.</span><span class="sxs-lookup"><span data-stu-id="7661a-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="7661a-152">В средстве просмотра необходимых компонентов System Center Operations Manager выберите компоненты System Center, которые необходимо установить: (**сервер**; **Консоль**; и **PowerShell**), а затем нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="7661a-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="7661a-153">Убедитесь, что отсутствуют блокирующие проблемы, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7661a-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="7661a-154">Если возникла проблема с блокировкой, устраните проблему и нажмите кнопку **проверить** , чтобы повторно запустить проверку.</span><span class="sxs-lookup"><span data-stu-id="7661a-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="7661a-155">В программе установки System Center Operations Manager щелкните **установить Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="7661a-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="7661a-156">В мастере установки System Center Operations Manager на странице **Добро пожаловать в мастер установки System Center Operations Manager** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="7661a-157">На странице лицензионного **соглашения** установите флажок **я принимаю условия лицензионного соглашения** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="7661a-158">На странице **Регистрация продукта** введите свое имя в поле **имя пользователя** и имя Организации в поле **Организация** .</span><span class="sxs-lookup"><span data-stu-id="7661a-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="7661a-159">Введите ключ продукта System Center Operations Manager в поле **введите 25-значный ключ** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="7661a-160">На странице **Выборочная установка** выберите устанавливаемые параметры System Center и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="7661a-161">Необходимо выбрать **сервер управления**, **пользовательские интерфейсы**и **веб-консоль** для установки.</span><span class="sxs-lookup"><span data-stu-id="7661a-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="7661a-162">**База данных** не должна быть выбрана и не должна устанавливаться.</span><span class="sxs-lookup"><span data-stu-id="7661a-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="7661a-163">На странице **экземпляр сервера базы данных SC** убедитесь, что имя компьютера, на котором установлены базы данных Operations Manager, отображается в поле **сервер System Center Database Server** .</span><span class="sxs-lookup"><span data-stu-id="7661a-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="7661a-164">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-164">Click **Next**.</span></span>

10. <span data-ttu-id="7661a-165">На странице **учетная запись действия сервера управления** выберите **учетную запись домена или локального компьютера** , а затем введите соответствующие значения в поля **учетная запись пользователя**, **пароль**, **домен или локальный компьютер** .</span><span class="sxs-lookup"><span data-stu-id="7661a-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="7661a-166">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-166">Click **Next**.</span></span>

11. <span data-ttu-id="7661a-167">На странице " **учетная запись службы SDK и настройки** " выберите **Доменная или локальная учетная запись компьютера** , а затем введите соответствующие значения в поля **учетная запись пользователя**, **пароль**, **домен или локальный компьютер** .</span><span class="sxs-lookup"><span data-stu-id="7661a-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="7661a-168">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-168">Click **Next**.</span></span>

12. <span data-ttu-id="7661a-169">На странице " **отчеты об ошибках Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="7661a-170">На странице **программы улучшения качества программного** обеспечения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="7661a-171">На странице " **все готово для установки программы** " нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="7661a-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="7661a-172">На странице **Завершение установки System Center Operations Manager** снимите флажок **резервный ключ шифрования** и **Запустите консоль** , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7661a-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="7661a-173">В программе установки System Center Operations Manager нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="7661a-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="7661a-174">Установка System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7661a-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="7661a-175">После установки и настройки консоли System Center Operations Manager необходимо установить System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="7661a-176">Если вы используете SQL Server 2008 R2 в качестве внутренней базы данных Operations Manager, то это означает, что необходимо сначала внести временное изменение в группу безопасности, связанную с SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="7661a-177">При использовании SQL Server 2008 R2 необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7661a-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="7661a-178">В меню **Пуск** выберите пункт **Администрирование** и щелкните **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="7661a-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="7661a-179">В диспетчере серверов разверните узел **Конфигурация**, узел **Локальные пользователи и группы** и щелкните элемент **Группы**.</span><span class="sxs-lookup"><span data-stu-id="7661a-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="7661a-180">Откройте следующую группу, где ATL – SC – 001 представляет имя вашего компьютера, а ARCHINST представляет экземпляр SQL Server для базы данных System Center: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="7661a-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="7661a-181">Щелкните группу правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="7661a-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="7661a-182">Переименуйте группу, удалив \*\* \_50\*\* из имени группы.</span><span class="sxs-lookup"><span data-stu-id="7661a-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="7661a-183">Пример: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="7661a-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="7661a-184">Закройте Диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="7661a-184">Close Server Manager.</span></span>

<span data-ttu-id="7661a-185">На этом шаге вы готовы установить System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7661a-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="7661a-186">Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="7661a-186">To do this:</span></span>

1.  <span data-ttu-id="7661a-187">На установочном носителе System Center Operations Manager 2007 R2 дважды щелкните **исполняемый файл SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="7661a-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="7661a-188">В программе установки System Center Operations Manager 2007 R2 щелкните **установить Отчеты Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="7661a-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="7661a-189">В мастере настройки отчетов System Center Operations Manager 2007 R2 на странице " **Добро пожаловать в систему отчетов Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="7661a-190">На странице Лицензионное **соглашение** установите флажок **я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="7661a-191">На странице **Регистрация продукта** убедитесь, что ваше имя и имя вашей организации отображаются в полях **имя пользователя** и **Организация** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="7661a-192">На странице **Настройка установки** выберите пункт **сервер отчетов** , а затем выберите **этот компонент и все зависимые компоненты, которые будут установлены на локальный жесткий**диск.</span><span class="sxs-lookup"><span data-stu-id="7661a-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="7661a-193">Нажмите кнопку **хранилище данных** и выберите **компонент будет недоступен**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="7661a-194">На странице **Подключение к корневому серверу управления** введите имя корневого сервера управления Operations Manager в поле **корневой сервер управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="7661a-195">На странице **Подключение к хранилищу данных Operations Manager** введите экземпляр SQL Server, на котором размещено хранилище данных в поле **экземпляр SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="7661a-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="7661a-196">(Если хранилище данных расположено в экземпляре по умолчанию, просто введите имя сервера, например: ATL-SQL-001.) Убедитесь, что имя базы данных **оператионсманажердв** отображается в поле **имя** , а этот порт **1433** отображается в поле **порт SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="7661a-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="7661a-197">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-197">Click **Next**.</span></span>

9.  <span data-ttu-id="7661a-198">На странице **экземпляра SQL Server Reporting** Services выберите сервер отчетов SQL Server в раскрывающемся списке **введите сервер служб отчетов SQL** Server, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="7661a-199">На странице "запись **для учетной записи хранилища данных** " введите имя и пароль пользователя, которому изначально назначены разрешения на запись для хранилища данных в полях **учетная запись пользователя** и **пароль** .</span><span class="sxs-lookup"><span data-stu-id="7661a-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="7661a-200">Выберите домен пользователя из раскрывающегося списка **домен** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="7661a-201">На странице **учетная запись для чтения данных** введите имя и пароль учетной записи пользователя, которая будет использоваться при запросе службами SQL Reporting Services хранилища данных в полях **учетная запись пользователя** и **пароль** .</span><span class="sxs-lookup"><span data-stu-id="7661a-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="7661a-202">Выберите домен учетной записи из раскрывающегося списка **домен** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="7661a-203">На странице " **отчеты о рабочих данных** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="7661a-204">На странице " **обновление Майкрософт** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7661a-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="7661a-205">На странице " **все готово для установки программы** " нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="7661a-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="7661a-206">На странице **Завершение работы мастера установки компонентов отчетов Operations Manager** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7661a-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="7661a-207">В программе установки System Center Operations Manager 2007 R2 нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="7661a-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="7661a-208">После установки средства System Center Reporting выполните следующую процедуру, чтобы сбросить имя группы безопасности, связанной с SQL Server Reporting.</span><span class="sxs-lookup"><span data-stu-id="7661a-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="7661a-209">Опять же, эту процедуру необходимо выполнить, только если вы используете SQL Server:</span><span class="sxs-lookup"><span data-stu-id="7661a-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="7661a-210">В меню **Пуск** выберите пункт **Администрирование** и щелкните **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="7661a-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="7661a-211">В диспетчере серверов разверните узел **Конфигурация**, узел **Локальные пользователи и группы** и щелкните элемент **Группы**.</span><span class="sxs-lookup"><span data-stu-id="7661a-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="7661a-212">Откройте следующую группу, где ATL – SC – 001 представляет имя вашего компьютера, а ARCHINST представляет экземпляр SQL Server для баз данных архивации и мониторинга: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="7661a-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="7661a-213">Щелкните группу правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="7661a-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="7661a-214">Переименуйте группу, добавив \*\* \_50\*\* в конец имени группы, непосредственно перед именем экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7661a-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="7661a-215">Пример: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="7661a-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="7661a-216">Закройте Диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="7661a-216">Close Server Manager.</span></span>

<span data-ttu-id="7661a-217">Если открыта консоль System Center Operations Center, необходимо закрыть приложение и перезапустить его; Если этого не сделать, вкладка **отчеты** не будет отображаться в пользовательском интерфейсе консоли операций.</span><span class="sxs-lookup"><span data-stu-id="7661a-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="7661a-218">Обратите внимание, что после первого перезапуска консоли операций может пройти несколько минут, прежде чем все отчеты мониторинга будут отображаться на вкладке **отчеты** .</span><span class="sxs-lookup"><span data-stu-id="7661a-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

