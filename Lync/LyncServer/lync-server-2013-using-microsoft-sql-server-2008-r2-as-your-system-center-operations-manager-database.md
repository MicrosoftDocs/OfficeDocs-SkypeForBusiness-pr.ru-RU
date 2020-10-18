---
title: 'Lync Server 2013: использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager'
description: 'Lync Server 2013: использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager.'
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
ms.openlocfilehash: 870c079e7e5e871fc62358e9bdd21653193fad7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580355"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="8b95e-103">Использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b95e-103">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b95e-104">_**Последнее изменение темы:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="8b95e-104">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="8b95e-105">Чтобы использовать SQL Server 2008 R2 в качестве серверной базы данных, выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8b95e-105">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="8b95e-106">Настройка SQL Server 2008 R2 и SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8b95e-106">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="8b95e-107">Прежде чем приступить к установке System Center Operations Manager, необходимо внести два изменения в конфигурацию SQL Server 2008 R2 и службы SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-107">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="8b95e-108">(Эти изменения необходимы только в том случае, если в качестве базы данных Operations Manager используется SQL Server 2008 R2). Сначала выполните следующие действия на компьютере, на котором будет размещаться база данных Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="8b95e-108">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="8b95e-109">В меню **Пуск** щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-109">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8b95e-110">В диалоговом окне **выполнить** введите **C: \\ Program Files \\ Microsoft SQL Server \\ MSRS10 \_ 50. ARCHINST \\ Reporting Services \\ ReportServer** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8b95e-110">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="8b95e-111">В папке **ReportServer** откройте файл **rsreportserver.config** в блокноте или любом другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="8b95e-111">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="8b95e-112">В начале файла отображается ряд узлов "Добавление ключа".</span><span class="sxs-lookup"><span data-stu-id="8b95e-112">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="8b95e-113">Найдите запись, которая начинает \*\* \< добавлять ключ = "секуреконнектионлевел"\*\* , и присвойте этому параметру значение **0**:</span><span class="sxs-lookup"><span data-stu-id="8b95e-113">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="8b95e-114">Сохраните файл **rsreportserver.config** а затем закройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="8b95e-114">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="8b95e-115">После обновления файла конфигурации сервера отчетов необходимо назначить правильный сертификат службам отчетов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b95e-115">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="8b95e-116">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8b95e-116">To do that:</span></span>

1.  <span data-ttu-id="8b95e-117">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft SQL Server 2008 R2**и **средства настройки**, а затем щелкните **Диспетчер конфигураций Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-117">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="8b95e-118">В диалоговом окне **Подключение к конфигурации служб Reporting Services** убедитесь, что имя сервера отображается в поле **имя сервера** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-118">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="8b95e-119">Выберите экземпляр SQL Server, на котором будет размещаться база данных Operations Manager (например, **ARCHINST**), из раскрывающегося списка **экземпляр сервера отчетов** и нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-119">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="8b95e-120">В диспетчере конфигурации служб Reporting Services щелкните **URL-адрес веб-службы**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-120">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="8b95e-121">На странице **URL-адрес веб-службы** выберите сертификат, который будет использоваться для служб отчетов, в раскрывающемся списке **SSL-сертификат** , а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-121">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="8b95e-122">Через несколько секунд вы увидите пару URL-адресов, перечисленных в разделе **URL-адреса веб-службы сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-122">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="8b95e-123">Щелкните оба URL-адреса, чтобы убедиться, что вы можете получить доступ к службам SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-123">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="8b95e-124">Закройте Диспетчер конфигураций служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-124">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="8b95e-125">Создание базы данных System Center Operations Manager для использования с SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8b95e-125">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="8b95e-126">Если вы хотите настроить System Center Operations Manager для использования базы данных SQL Server 2008 R2, необходимо создать базу данных Operations Manager на компьютере с SQL Server 2008 R2, выполнив команду "вручную".</span><span class="sxs-lookup"><span data-stu-id="8b95e-126">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="8b95e-127">(Опять же, эти действия не требуются, если вы используете SQL Server 2005 или SQL Server 2008 в качестве внутренней базы данных.)</span><span class="sxs-lookup"><span data-stu-id="8b95e-127">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="8b95e-128">Чтобы вручную создать базу данных Operations Manager, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8b95e-128">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="8b95e-129">На установочном носителе System Center Operations Manager 2007 R2 в папке Суппорттулс \\ AMD64 дважды щелкните элемент **DBCreateWizard.exe**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-129">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="8b95e-130">В мастере настройки базы данных на странице **Добро пожаловать в мастер настройки базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-130">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="8b95e-131">На странице **сведения о базе данных** оставьте все параметры как есть, а затем нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-131">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="8b95e-132">На странице " **Конфигурация группы управления** " введите имя группы управления (например, " **наблюдение за Lync Server**") в поле **имя группы управления** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-132">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="8b95e-133">На странице " **отчеты об ошибках Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-133">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="8b95e-134">На странице **Сводка** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-134">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="8b95e-135">Создание хранилища данных System Center Operations Manager для использования с SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8b95e-135">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="8b95e-136">В состав Microsoft Lync Server 2013 входит три новых отчета System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="8b95e-136">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="8b95e-137">**Отчет о**     доступности в сценарии "от" до конца В этом отчете подробно описана доступность и время работы для ключевых служб Lync Server, таких как регистрация или присутствие.</span><span class="sxs-lookup"><span data-stu-id="8b95e-137">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="8b95e-138">**Отчет о емкости**     С помощью данных счетчиков производительности этот отчет показывает тенденции для компонентов системы, таких как доступность памяти и загрузка процессора.</span><span class="sxs-lookup"><span data-stu-id="8b95e-138">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="8b95e-139">**Отчет о**     компонентах В этом отчете представлены топ генераторов оповещений, сгруппированных по компонентам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b95e-139">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="8b95e-140">Чтобы использовать эти новые отчеты, необходимо установить хранилище данных System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8b95e-140">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="8b95e-141">(Хранилище данных обеспечивает долговременное хранение данных операций.) Чтобы использовать хранилище данных с SQL Server 2008 R2, выполните следующие действия на компьютере, на котором размещается база данных SQL Server:</span><span class="sxs-lookup"><span data-stu-id="8b95e-141">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="8b95e-142">На установочном носителе System Center Operations Manager в папке Setup \\ суппорттулс \\ AMD64 дважды щелкните **DBCreateWizard.exe**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-142">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="8b95e-143">В мастере настройки базы данных на странице **Добро пожаловать в мастер настройки базы данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-143">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="8b95e-144">На странице **сведения о базе данных** выберите **базу данных хранилища данных Operations Manager** в раскрывающемся списке **тип базы данных** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-144">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="8b95e-145">На странице **Сводка** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-145">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="8b95e-146">Установка консоли System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="8b95e-146">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="8b95e-147">Консоль Operations Manager — это основное средство, используемое для управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8b95e-147">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="8b95e-148">Перед установкой консоли Operations Manager убедитесь, что установлена поддерживаемая версия SQL Server и служба SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-148">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="8b95e-149">Также рекомендуется запустить диспетчер конфигурации служб отчетов SQL Server, чтобы убедиться, что служба Reporting Services установлена и настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="8b95e-149">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="8b95e-150">Установка консоли System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="8b95e-150">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="8b95e-151">На носителе программы установки System Center Operations Manager дважды щелкните **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-151">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="8b95e-152">В программе установки System Center Operations Manager 2007 R2 щелкните **проверить предварительные требования**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-152">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="8b95e-153">В средстве просмотра необходимых компонентов System Center Operations Manager выберите компоненты System Center, которые необходимо установить: (**сервер**; **Консоль**; и **PowerShell**), а затем нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-153">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="8b95e-154">Убедитесь, что отсутствуют блокирующие проблемы, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-154">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="8b95e-155">Если возникла проблема с блокировкой, устраните проблему и нажмите кнопку **проверить** , чтобы повторно запустить проверку.</span><span class="sxs-lookup"><span data-stu-id="8b95e-155">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="8b95e-156">В программе установки System Center Operations Manager щелкните **установить Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-156">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="8b95e-157">В мастере установки System Center Operations Manager на странице **Добро пожаловать в мастер установки System Center Operations Manager** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-157">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="8b95e-158">На странице лицензионного **соглашения** установите флажок **я принимаю условия лицензионного соглашения** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-158">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="8b95e-159">На странице **Регистрация продукта** введите свое имя в поле **имя пользователя** и имя Организации в поле **Организация** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-159">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="8b95e-160">Введите ключ продукта System Center Operations Manager в поле **введите 25-значный ключ** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-160">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="8b95e-161">На странице **Выборочная установка** выберите устанавливаемые параметры System Center и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-161">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="8b95e-162">Необходимо выбрать **сервер управления**, **пользовательские интерфейсы**и **веб-консоль** для установки.</span><span class="sxs-lookup"><span data-stu-id="8b95e-162">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="8b95e-163">**База данных** не должна быть выбрана и не должна устанавливаться.</span><span class="sxs-lookup"><span data-stu-id="8b95e-163">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="8b95e-164">На странице **экземпляр сервера базы данных SC** убедитесь, что имя компьютера, на котором установлены базы данных Operations Manager, отображается в поле **сервер System Center Database Server** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-164">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="8b95e-165">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-165">Click **Next**.</span></span>

10. <span data-ttu-id="8b95e-166">На странице **учетная запись действия сервера управления** выберите **учетную запись домена или локального компьютера** , а затем введите соответствующие значения в поля **учетная запись пользователя**, **пароль**, **домен или локальный компьютер** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-166">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="8b95e-167">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-167">Click **Next**.</span></span>

11. <span data-ttu-id="8b95e-168">На странице " **учетная запись службы SDK и настройки** " выберите **Доменная или локальная учетная запись компьютера** , а затем введите соответствующие значения в поля **учетная запись пользователя**, **пароль**, **домен или локальный компьютер** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-168">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="8b95e-169">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-169">Click **Next**.</span></span>

12. <span data-ttu-id="8b95e-170">На странице " **отчеты об ошибках Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-170">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="8b95e-171">На странице **программы улучшения качества программного** обеспечения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-171">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="8b95e-172">На странице " **все готово для установки программы** " нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-172">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="8b95e-173">На странице **Завершение установки System Center Operations Manager** снимите флажок **резервный ключ шифрования** и **Запустите консоль** , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-173">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="8b95e-174">В программе установки System Center Operations Manager нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-174">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="8b95e-175">Установка System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8b95e-175">Installing System Center Reporting Services</span></span>

<span data-ttu-id="8b95e-176">После установки и настройки консоли System Center Operations Manager необходимо установить System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-176">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="8b95e-177">Если вы используете SQL Server 2008 R2 в качестве внутренней базы данных Operations Manager, то это означает, что необходимо сначала внести временное изменение в группу безопасности, связанную с SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-177">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="8b95e-178">При использовании SQL Server 2008 R2 необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8b95e-178">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="8b95e-179">В меню **Пуск** выберите пункт **Администрирование** и щелкните **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-179">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="8b95e-180">В диспетчере серверов разверните узел **Конфигурация**, узел **Локальные пользователи и группы** и щелкните элемент **Группы**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-180">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="8b95e-181">Откройте следующую группу, где ATL – SC – 001 представляет имя вашего компьютера, а ARCHINST представляет экземпляр SQL Server для базы данных System Center: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10 \_ 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-181">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="8b95e-182">Щелкните группу правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-182">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="8b95e-183">Переименуйте группу, удалив \*\* \_ 50\*\* из имени группы.</span><span class="sxs-lookup"><span data-stu-id="8b95e-183">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="8b95e-184">Пример: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-184">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="8b95e-185">Закройте Диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="8b95e-185">Close Server Manager.</span></span>

<span data-ttu-id="8b95e-186">На этом шаге вы готовы установить System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8b95e-186">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="8b95e-187">Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="8b95e-187">To do this:</span></span>

1.  <span data-ttu-id="8b95e-188">На установочном носителе System Center Operations Manager 2007 R2 дважды щелкните **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-188">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="8b95e-189">В программе установки System Center Operations Manager 2007 R2 щелкните **установить Отчеты Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-189">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="8b95e-190">В мастере настройки отчетов System Center Operations Manager 2007 R2 на странице " **Добро пожаловать в систему отчетов Operations Manager** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-190">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="8b95e-191">На странице Лицензионное **соглашение** установите флажок **я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-191">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="8b95e-192">На странице **Регистрация продукта** убедитесь, что ваше имя и имя вашей организации отображаются в полях **имя пользователя** и **Организация** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-192">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="8b95e-193">На странице **Настройка установки** выберите пункт **сервер отчетов** , а затем выберите **этот компонент и все зависимые компоненты, которые будут установлены на локальный жесткий**диск.</span><span class="sxs-lookup"><span data-stu-id="8b95e-193">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="8b95e-194">Нажмите кнопку **хранилище данных** и выберите **компонент будет недоступен**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-194">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="8b95e-195">На странице **Подключение к корневому серверу управления** введите имя корневого сервера управления Operations Manager в поле **корневой сервер управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-195">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="8b95e-196">На странице **Подключение к хранилищу данных Operations Manager** введите экземпляр SQL Server, на котором размещено хранилище данных в поле **экземпляр SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-196">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="8b95e-197">(Если хранилище данных расположено в экземпляре по умолчанию, просто введите имя сервера, например: ATL-SQL-001.) Убедитесь, что имя базы данных **оператионсманажердв** отображается в поле **имя** , а этот порт **1433** отображается в поле **порт SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-197">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="8b95e-198">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-198">Click **Next**.</span></span>

9.  <span data-ttu-id="8b95e-199">На странице **экземпляра SQL Server Reporting** Services выберите сервер отчетов SQL Server в раскрывающемся списке **введите сервер служб отчетов SQL** Server, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-199">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="8b95e-200">На странице "запись **для учетной записи хранилища данных** " введите имя и пароль пользователя, которому изначально назначены разрешения на запись для хранилища данных в полях **учетная запись пользователя** и **пароль** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-200">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="8b95e-201">Выберите домен пользователя из раскрывающегося списка **домен** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-201">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="8b95e-202">На странице **учетная запись для чтения данных** введите имя и пароль учетной записи пользователя, которая будет использоваться при запросе службами SQL Reporting Services хранилища данных в полях **учетная запись пользователя** и **пароль** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-202">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="8b95e-203">Выберите домен учетной записи из раскрывающегося списка **домен** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-203">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="8b95e-204">На странице " **отчеты о рабочих данных** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-204">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="8b95e-205">На странице " **обновление Майкрософт** " нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-205">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="8b95e-206">На странице " **все готово для установки программы** " нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-206">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="8b95e-207">На странице **Завершение работы мастера установки компонентов отчетов Operations Manager** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-207">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="8b95e-208">В программе установки System Center Operations Manager 2007 R2 нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-208">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="8b95e-209">После установки средства System Center Reporting выполните следующую процедуру, чтобы сбросить имя группы безопасности, связанной с SQL Server Reporting.</span><span class="sxs-lookup"><span data-stu-id="8b95e-209">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="8b95e-210">Опять же, эту процедуру необходимо выполнить, только если вы используете SQL Server:</span><span class="sxs-lookup"><span data-stu-id="8b95e-210">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="8b95e-211">В меню **Пуск** выберите пункт **Администрирование** и щелкните **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-211">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="8b95e-212">В диспетчере серверов разверните узел **Конфигурация**, узел **Локальные пользователи и группы** и щелкните элемент **Группы**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-212">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="8b95e-213">Откройте следующую группу, где ATL – SC – 001 представляет имя вашего компьютера, а ARCHINST представляет экземпляр SQL Server для баз данных архивации и мониторинга: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-213">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="8b95e-214">Щелкните группу правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-214">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="8b95e-215">Переименуйте группу, добавив \*\* \_ 50\*\* в конец имени группы, непосредственно перед именем экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b95e-215">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="8b95e-216">Пример: **SQLServerReportServerUser $ ATL – SC – 001 $ MSRS10 \_ 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="8b95e-216">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="8b95e-217">Закройте Диспетчер серверов.</span><span class="sxs-lookup"><span data-stu-id="8b95e-217">Close Server Manager.</span></span>

<span data-ttu-id="8b95e-218">Если открыта консоль System Center Operations Center, необходимо закрыть приложение и перезапустить его; Если этого не сделать, вкладка **отчеты** не будет отображаться в пользовательском интерфейсе консоли операций.</span><span class="sxs-lookup"><span data-stu-id="8b95e-218">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="8b95e-219">Обратите внимание, что после первого перезапуска консоли операций может пройти несколько минут, прежде чем все отчеты мониторинга будут отображаться на вкладке **отчеты** .</span><span class="sxs-lookup"><span data-stu-id="8b95e-219">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

