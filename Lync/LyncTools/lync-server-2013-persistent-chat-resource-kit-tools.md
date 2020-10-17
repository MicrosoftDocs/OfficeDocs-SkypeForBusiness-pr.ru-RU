---
title: Средства набора ресурсов сохраняемого чата Lync Server 2013
description: Средства набора ресурсов сохраняемого чата Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542355"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="70f73-103">Средства набора ресурсов сохраняемого чата Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70f73-103">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70f73-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="70f73-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="70f73-105">Средства набора ресурсов сохраняемого чата Lync Server 2013 помогают упростить выполнение повседневных задач для ИТ ИТ ИТ, которые развертывают и управляют Lync Server 2013 для сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-105">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="70f73-106">В дополнение к инструкциям по установке в этом разделе описывается назначение каждого средства и приводятся примеры его использования.</span><span class="sxs-lookup"><span data-stu-id="70f73-106">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="70f73-107">Установка средств набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="70f73-107">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="70f73-108">Для установки средств набора ресурсов Lync Server 2013, скачайте **PersistentChatReskit.msi**.</span><span class="sxs-lookup"><span data-stu-id="70f73-108">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="70f73-109">Запустите **PersistentChatReskit.msi** , чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="70f73-109">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="70f73-110">MSI устанавливает все средства, указанные в следующем пути: \\ **Program Files \\ Microsoft Lync Server 2013 \\ Resource Chat Server Resource Kit**.</span><span class="sxs-lookup"><span data-stu-id="70f73-110">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="70f73-111">В этой папке есть инструменты, которые представляют собой автономные исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="70f73-111">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="70f73-112">Средства, у которых также есть файлы, находятся в своих вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="70f73-112">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="70f73-113">После установки средств набора ресурсов Lync Server 2013, необходимо установить <STRONG>PsExec.exe</STRONG> и скопировать <STRONG>PsExec.exe</STRONG> по следующему пути: \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ сервер ресурсов кит\чатстресстул</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="70f73-113">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="70f73-114">Если вы не копируете <STRONG>PsExec.exe</STRONG>, средство стрессового чата выполняет исключение ошибки и не выполняется должным образом.</span><span class="sxs-lookup"><span data-stu-id="70f73-114">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="70f73-115">Перед запуском средства убедитесь, что выполнены соответствующие требования.</span><span class="sxs-lookup"><span data-stu-id="70f73-115">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="70f73-116">Более подробную информацию об установке <STRONG>PsExec.exe</STRONG>можно узнать в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .</span><span class="sxs-lookup"><span data-stu-id="70f73-116">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="70f73-117">Поддерживаемые среды</span><span class="sxs-lookup"><span data-stu-id="70f73-117">Supported Environments</span></span>

<span data-ttu-id="70f73-118">Для оптимальной производительности Lync Server 2013, средства набора ресурсов необходимо установить в той же среде и с теми же спецификациями, что и для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70f73-118">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="70f73-119">Общие сведения о средствах набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="70f73-119">Resource Kit Tools Overview</span></span>

<span data-ttu-id="70f73-120">Ниже приведены средства, доступные в наборе ресурсов сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70f73-120">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="70f73-121">В следующем разделе представлено описание каждого средства, включая требования и примеры использования.</span><span class="sxs-lookup"><span data-stu-id="70f73-121">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="70f73-122">аффчекк</span><span class="sxs-lookup"><span data-stu-id="70f73-122">AffCheck</span></span>

  - <span data-ttu-id="70f73-123">чатмониторингсуммари</span><span class="sxs-lookup"><span data-stu-id="70f73-123">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="70f73-124">Средство Чатстресс</span><span class="sxs-lookup"><span data-stu-id="70f73-124">ChatStress Tool</span></span>

  - <span data-ttu-id="70f73-125">чатупградеверифиер</span><span class="sxs-lookup"><span data-stu-id="70f73-125">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="70f73-126">чатусажерепорт</span><span class="sxs-lookup"><span data-stu-id="70f73-126">ChatUsageReport</span></span>

  - <span data-ttu-id="70f73-127">счедулеадсинкфорпринЦипал</span><span class="sxs-lookup"><span data-stu-id="70f73-127">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="70f73-128">аффчекк</span><span class="sxs-lookup"><span data-stu-id="70f73-128">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="70f73-129">Описание</span><span class="sxs-lookup"><span data-stu-id="70f73-129">Description</span></span>

<span data-ttu-id="70f73-130">Средство Аффчекк проверяет, совпадают записи принадлежности пользователей и групп сохраняемого чата для доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70f73-130">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="70f73-131">Требования</span><span class="sxs-lookup"><span data-stu-id="70f73-131">Requirements</span></span>

<span data-ttu-id="70f73-132">Средство устанавливается вместе с установщиком Персистентчатрескит на компьютере, присоединенном к домену.</span><span class="sxs-lookup"><span data-stu-id="70f73-132">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="70f73-133">Учетная запись пользователя, с которой запускается средство, должна иметь доступ на чтение к базе данных сохраняемого чата и доменным службам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70f73-133">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="70f73-134">Применение</span><span class="sxs-lookup"><span data-stu-id="70f73-134">Usage</span></span>

<span data-ttu-id="70f73-135">Настройте файл AffCheck.exe.config в соответствии с инструкциями в файле конфигурации и запустите средство Аффчекк без параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="70f73-135">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="70f73-136">Ниже приведено содержимое AffCheck.exe.config по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70f73-136">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="70f73-137">**AffCheck.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="70f73-137">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="70f73-138">чатмониторингсуммари</span><span class="sxs-lookup"><span data-stu-id="70f73-138">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="70f73-139">Описание</span><span class="sxs-lookup"><span data-stu-id="70f73-139">Description</span></span>

<span data-ttu-id="70f73-140">Средство Персистентчатмониторингсуммари перемещает данные мониторинга сохраняемого чата из базы данных мониторинга в указанный CSV-файл журнала.</span><span class="sxs-lookup"><span data-stu-id="70f73-140">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="70f73-141">CSV-файл будет содержать разбиение сеансов сохраняемого чата по количеству сеансов, успешных сеансов, неожиданным сбоям, ожидаемым отказам и разбиению неожиданного сбоя по ИДЕНТИФИКАТОРу диагностики, количеству сбоев и описанию сбоя.</span><span class="sxs-lookup"><span data-stu-id="70f73-141">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="70f73-142">Требования</span><span class="sxs-lookup"><span data-stu-id="70f73-142">Requirements</span></span>

<span data-ttu-id="70f73-143">Установите средства набора ресурсов сохраняемого чата на компьютер, подключенный к домену, который имеет доступ к базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f73-143">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="70f73-144">Учетная запись пользователя, с помощью которой запускается средство, должна иметь доступ на чтение к базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f73-144">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="70f73-145">Файл PersistentChatMonitoringSummary.exe.config должен содержать \<connectionStrings\> раздел, определяющий строку подключения к базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f73-145">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="70f73-146">Он также должен содержать ключ для Персистентчатендпоинтури, для которого будут собираться данные мониторинга, и путь к файлу для CSV-файла, который будет создан.</span><span class="sxs-lookup"><span data-stu-id="70f73-146">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="70f73-147">Ознакомьтесь с примерами установленного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70f73-147">Refer to the installed config file for examples.</span></span> <span data-ttu-id="70f73-148">Файл должен находиться в том же каталоге, что и средство.</span><span class="sxs-lookup"><span data-stu-id="70f73-148">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="70f73-149">Применение</span><span class="sxs-lookup"><span data-stu-id="70f73-149">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="70f73-150">Эти параметры определяют выбор данных:</span><span class="sxs-lookup"><span data-stu-id="70f73-150">These parameters define the selection of data:</span></span>

<span data-ttu-id="70f73-151">**StartDateTime:** Дополнительно указывает дату начала периода выбора.</span><span class="sxs-lookup"><span data-stu-id="70f73-151">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="70f73-152">Значение по умолчанию: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="70f73-152">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="70f73-153">**EndDateTime:** При необходимости указывается последняя дата периода выбора.</span><span class="sxs-lookup"><span data-stu-id="70f73-153">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="70f73-154">По умолчанию: Now</span><span class="sxs-lookup"><span data-stu-id="70f73-154">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="70f73-155">Пример</span><span class="sxs-lookup"><span data-stu-id="70f73-155">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="70f73-156">Средство нагрузочного тестирования сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="70f73-156">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="70f73-157">Описание</span><span class="sxs-lookup"><span data-stu-id="70f73-157">Description</span></span>

<span data-ttu-id="70f73-158">Средство стрессового чата позволяет легко имитировать использование сохраняемого чата для тестирования реальной производительности, в том числе разнообразных пользовательских моделей в соответствии с ожидаемыми сценариями использования.</span><span class="sxs-lookup"><span data-stu-id="70f73-158">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="70f73-159">Требования</span><span class="sxs-lookup"><span data-stu-id="70f73-159">Requirements</span></span>

<span data-ttu-id="70f73-160">Установите средства набора ресурсов сохраняемого чата на компьютер, присоединенный к домену, который имеет доступ к фоновой базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-160">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="70f73-161">В дополнение к данному *контроллеру* компьютера потребуется несколько компьютеров *загрузчика* .</span><span class="sxs-lookup"><span data-stu-id="70f73-161">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="70f73-162">Для каждых 10 000 пользователей в пользовательской модели вам потребуется по крайней мере 4 ГБ свободного ОЗУ на компьютере загрузчика.</span><span class="sxs-lookup"><span data-stu-id="70f73-162">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="70f73-163">Например, для запуска с 80K пользователям потребуется около 32 ГБ ОЗУ на всех машинах загрузчика.</span><span class="sxs-lookup"><span data-stu-id="70f73-163">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="70f73-164">Рекомендуется использовать по крайней мере три компьютера загрузчика, независимо от ожидаемой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="70f73-164">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="70f73-165">На компьютерах загрузчика должна быть установлена платформа .NET 4,5 Framework, а также распространяемый компонент Visual C++ 2012.</span><span class="sxs-lookup"><span data-stu-id="70f73-165">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="70f73-166">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="70f73-166">Configuration</span></span>

<span data-ttu-id="70f73-167">Скопируйте файлы Чатстресстул в общую папку, доступную на всех машинах загрузчика.</span><span class="sxs-lookup"><span data-stu-id="70f73-167">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="70f73-168">Создайте пользователей и каналы для использования при нагрузочном запуске:</span><span class="sxs-lookup"><span data-stu-id="70f73-168">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="70f73-169">Создайте как можно больше пользователей, для которых будет вызываться модель пользователя, включите их для Lync, а затем установите для их политики сохраняемого чата значение Enabled.</span><span class="sxs-lookup"><span data-stu-id="70f73-169">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="70f73-170">Создайте категорию для каналов стресса, а затем создайте столько комнат, сколько необходимо для этой категории.</span><span class="sxs-lookup"><span data-stu-id="70f73-170">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="70f73-171">У категории должны быть все погрузки пользователей в список **разрешенных** пользователей (при добавлении подразделений), а для рабочих комнат — значение " **Открыть**".</span><span class="sxs-lookup"><span data-stu-id="70f73-171">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="70f73-172">Мы рекомендуем создавать лишние помещения для нагрузки.</span><span class="sxs-lookup"><span data-stu-id="70f73-172">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="70f73-173">Вы можете создавать комнаты 50 000 с помощью следующей команды интерфейса командной строки Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="70f73-173">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="70f73-174">Измените файлы конфигурации в соответствии с вашей топологией:</span><span class="sxs-lookup"><span data-stu-id="70f73-174">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="70f73-175">В **LoaderProcess.exe.config**замените имя "Controller.contoso.com" на полное доменное имя компьютера контроллера (полное доменное имя).</span><span class="sxs-lookup"><span data-stu-id="70f73-175">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="70f73-176">В **StressLauncher.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="70f73-176">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="70f73-177">Измените значение параметра "Лоадербинари" на путь к общей папке.</span><span class="sxs-lookup"><span data-stu-id="70f73-177">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="70f73-178">Замените "Админусер"/"Админпассворд" на учетные данные, которые имеют административный доступ к машинам загрузчика.</span><span class="sxs-lookup"><span data-stu-id="70f73-178">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="70f73-179">Замените "Чаннелкатегори" на имя категории, в которой созданы каналы нагрузки в.</span><span class="sxs-lookup"><span data-stu-id="70f73-179">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="70f73-180">Замените "Усернамепаттерн" и "Усерпассвордпаттерн" на шаблон, соответствующий вашим учетным данным пользователя.</span><span class="sxs-lookup"><span data-stu-id="70f73-180">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="70f73-181">{0} заменяется номером индекса пользователя.</span><span class="sxs-lookup"><span data-stu-id="70f73-181">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="70f73-182">Измените значение "Domain" на домен SIP для тестовой топологии.</span><span class="sxs-lookup"><span data-stu-id="70f73-182">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="70f73-183">Замените строку "ConnectionString" на строку подключения для внутренней базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-183">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="70f73-184">Замените "Усериндексстарт" индексом первого пользователя нагрузки.</span><span class="sxs-lookup"><span data-stu-id="70f73-184">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="70f73-185">Замените "Линкфкдн" на полное доменное имя интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="70f73-185">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="70f73-186">Измените список "machines", чтобы включить имена компьютеров для всех компьютеров загрузчика.</span><span class="sxs-lookup"><span data-stu-id="70f73-186">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="70f73-187">Измените значение baseAddress конечной точки службы (по умолчанию — "controller.contoso.com") до полного доменного имени компьютера контроллера.</span><span class="sxs-lookup"><span data-stu-id="70f73-187">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="70f73-188">Применение</span><span class="sxs-lookup"><span data-stu-id="70f73-188">Usage</span></span>

<span data-ttu-id="70f73-189">После завершения настройки откройте StressLauncher.exe на компьютере контроллера.</span><span class="sxs-lookup"><span data-stu-id="70f73-189">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="70f73-190">Вы можете запустить Стресслаунчер как любой пользователь.</span><span class="sxs-lookup"><span data-stu-id="70f73-190">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="70f73-191">Учетные данные, с которыми запускаются процессы загрузчика на машинах загрузчика, должны быть указаны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70f73-191">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="70f73-192">Кроме того, необходимо предоставить строку подключения, доступную для чтения, в фоновую базу данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-192">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="70f73-193">Если эта строка подключения использует встроенную проверку подлинности Windows, необходимо запустить Стресслаунчер в качестве пользователя, имеющего этот доступ.</span><span class="sxs-lookup"><span data-stu-id="70f73-193">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="70f73-194">При необходимости измените параметры пользовательской модели.</span><span class="sxs-lookup"><span data-stu-id="70f73-194">Alter the user model settings as needed.</span></span> <span data-ttu-id="70f73-195">Нажмите кнопку **начать загрузку** , чтобы начать выполнение.</span><span class="sxs-lookup"><span data-stu-id="70f73-195">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="70f73-196">Через минуту пользователи начнут войти в систему, а индикатор выполнения начнет заполняться.</span><span class="sxs-lookup"><span data-stu-id="70f73-196">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="70f73-197">На этом шаге контроллер может работать и принимать измерения производительности.</span><span class="sxs-lookup"><span data-stu-id="70f73-197">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="70f73-198">чатупградеверифиер</span><span class="sxs-lookup"><span data-stu-id="70f73-198">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="70f73-199">Описание</span><span class="sxs-lookup"><span data-stu-id="70f73-199">Description</span></span>

<span data-ttu-id="70f73-200">Чатупградеверифиер — это средство сравнения баз данных для сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-200">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="70f73-201">Средство сравнивает базу данных общения групп 2007 R2 или Group Chat 2010 (2007/2010Db) с базой данных сохраняемого чата 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="70f73-201">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="70f73-202">Средство проверит (по одному) каждую категорию, комнату сохраняемого чата и надстройку в версии 2007/2010Db, чтобы узнать, отображается ли она в 2013Db.</span><span class="sxs-lookup"><span data-stu-id="70f73-202">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="70f73-203">Сравнение включает проверку всех параметров для категории, комнаты чата или надстройки, любых субъектов в области в категории и любой участник роли в категории либо в комнате чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-203">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="70f73-204">Если категория или комната чата не отображаются правильно в 2013Db, то различия будут выводиться в файл конфликтов.</span><span class="sxs-lookup"><span data-stu-id="70f73-204">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="70f73-205">Если после обновления 2007/2010Db изменяется, а затем запускается это средство, в файл конфликтов будет выведено различие.</span><span class="sxs-lookup"><span data-stu-id="70f73-205">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="70f73-206">Обратите внимание, что это приложение является только средством сравнения баз данных и не проверяет процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="70f73-206">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="70f73-207">Требования</span><span class="sxs-lookup"><span data-stu-id="70f73-207">Requirements</span></span>

<span data-ttu-id="70f73-208">Установите средства набора ресурсов сохраняемого чата на компьютер, присоединенный к домену, который имеет доступ к внутренним базам данных сохраняемого чата (Предыдущая и текущая версии для сохраняемого чата).</span><span class="sxs-lookup"><span data-stu-id="70f73-208">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="70f73-209">Учетная запись пользователя, с помощью которой запускается средство, должна иметь доступ на чтение к базам данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-209">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="70f73-210">Файл ChatUpgradeVerifier.exe.config должен содержать либо параметр GroupChat2007R2Db, либо параметр GroupChat2010Db со строкой подключения к соответствующей базе данных группового чата (Groupchat 2007R2 или 2010).</span><span class="sxs-lookup"><span data-stu-id="70f73-210">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="70f73-211">Он также должен содержать параметр PersistentChat2013Db со строкой подключения к базе данных сохраняемого чата 2013.</span><span class="sxs-lookup"><span data-stu-id="70f73-211">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="70f73-212">Применение</span><span class="sxs-lookup"><span data-stu-id="70f73-212">Usage</span></span>

<span data-ttu-id="70f73-213">Запустите **чатупградеверифиер** без параметров.</span><span class="sxs-lookup"><span data-stu-id="70f73-213">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="70f73-214">Пример</span><span class="sxs-lookup"><span data-stu-id="70f73-214">Example</span></span>

<span data-ttu-id="70f73-215">![Выполнение ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Выполнение ChatUpgradeVerifier.exe.")</span><span class="sxs-lookup"><span data-stu-id="70f73-215">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="70f73-216">Отчет об использовании сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="70f73-216">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="70f73-217">Описание</span><span class="sxs-lookup"><span data-stu-id="70f73-217">Description</span></span>

<span data-ttu-id="70f73-218">Средство Чатусажерепорт создает HTML-отчет об использовании службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-218">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="70f73-219">Требования</span><span class="sxs-lookup"><span data-stu-id="70f73-219">Requirements</span></span>

<span data-ttu-id="70f73-220">Установите средства набора ресурсов сохраняемого чата на компьютер, присоединенный к домену, который имеет доступ к фоновой базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-220">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="70f73-221">Учетная запись пользователя, с которой запускается средство, должна иметь доступ на чтение к базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-221">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="70f73-222">Файл ChatUsageReport.exe.config должен содержать \<connectionStrings\> раздел, определяющий строку подключения для внутренней базы данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-222">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="70f73-223">Содержимое файла конфигурации по умолчанию включено в ссылку.</span><span class="sxs-lookup"><span data-stu-id="70f73-223">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="70f73-224">Применение</span><span class="sxs-lookup"><span data-stu-id="70f73-224">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="70f73-225">Эти параметры определяют выбор данных:</span><span class="sxs-lookup"><span data-stu-id="70f73-225">These parameters define the selection of data:</span></span>

<span data-ttu-id="70f73-226">**StartDate:** При необходимости определяет дату начала периода выбора в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="70f73-226">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="70f73-227">Значение по умолчанию: самая ранняя дата</span><span class="sxs-lookup"><span data-stu-id="70f73-227">Default: Earliest Date</span></span>

<span data-ttu-id="70f73-228">**Дата окончания:** При необходимости указывает дату окончания периода выбора в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="70f73-228">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="70f73-229">По умолчанию: Now</span><span class="sxs-lookup"><span data-stu-id="70f73-229">Default: Now</span></span>

<span data-ttu-id="70f73-230">Эти параметры определяют, как и какие данные отображаются:</span><span class="sxs-lookup"><span data-stu-id="70f73-230">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="70f73-231">**Топактивеусерс:** Если этот параметр указан, то отчет будет включать в себя n наиболее активных пользователей с точки зрения числа сообщений, которые пользователь опубликовал в комнате чата для выбранного периода.</span><span class="sxs-lookup"><span data-stu-id="70f73-231">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="70f73-232">По умолчанию: 10</span><span class="sxs-lookup"><span data-stu-id="70f73-232">Default: 10</span></span>

<span data-ttu-id="70f73-233">**Топактиверумс:** Если этот параметр указан, в отчет будут включены n большинства активных комнат чата с точки зрения числа сообщений, опубликованных в комнате за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-233">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="70f73-234">По умолчанию: 10</span><span class="sxs-lookup"><span data-stu-id="70f73-234">Default: 10</span></span>

<span data-ttu-id="70f73-235">**Леастактиверумс:** Если этот параметр указан, в отчет будут включены n наименее активные комнаты чата с точки зрения числа сообщений, опубликованных в комнате чата для выбранного периода.</span><span class="sxs-lookup"><span data-stu-id="70f73-235">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="70f73-236">В комнатах будет размещено по крайней мере одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="70f73-236">Rooms will have at least one message posted.</span></span> <span data-ttu-id="70f73-237">По умолчанию: 10</span><span class="sxs-lookup"><span data-stu-id="70f73-237">Default: 10</span></span>

<span data-ttu-id="70f73-238">**Румсинактивесинце:** Если этот параметр указан, отчет будет включать список комнат чата, которые были неактивны с момента указанной даты.</span><span class="sxs-lookup"><span data-stu-id="70f73-238">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="70f73-239">Значение по умолчанию: полное время</span><span class="sxs-lookup"><span data-stu-id="70f73-239">Default: Entire Time</span></span>

<span data-ttu-id="70f73-240">**Аутпутфолдер:** Папка, в которой будут размещены ChatUsageReport.html и изображения графиков.</span><span class="sxs-lookup"><span data-stu-id="70f73-240">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="70f73-241">Это значение должно быть определено в файле конфигурации или в командной строке.</span><span class="sxs-lookup"><span data-stu-id="70f73-241">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="70f73-242">Все значения параметров командной строки также можно указать в файле ChatUsageReport.exe.config, расположенном в том же каталоге, что и средство.</span><span class="sxs-lookup"><span data-stu-id="70f73-242">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="70f73-243">Если какое-либо значение указано как в файле конфигурации, так и в командной строке, значение в командной строке переопределит значение файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70f73-243">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="70f73-244">Output</span><span class="sxs-lookup"><span data-stu-id="70f73-244">Output</span></span>

<span data-ttu-id="70f73-245">Отчет всегда будет включать следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="70f73-245">The report will always include the following output:</span></span>

  - <span data-ttu-id="70f73-246">Первые n большинства активных комнат чата по количеству записей сообщений за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-246">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="70f73-247">Первые n наиболее активных пользователей по количеству записей сообщений за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-247">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="70f73-248">Первые n наименее активные комнаты чата по количеству записей сообщений за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-248">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="70f73-249">Комнаты чата, неактивные для всей жизни базы данных или с момента указанной даты.</span><span class="sxs-lookup"><span data-stu-id="70f73-249">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="70f73-250">Тенденция при отправке ежедневных сообщений за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-250">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="70f73-251">Еженедельное сообщение об тренде для выбранного периода.</span><span class="sxs-lookup"><span data-stu-id="70f73-251">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="70f73-252">Месячная тенденция при отправке сообщения за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-252">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="70f73-253">Общее количество записей в сообщениях за выбранный период.</span><span class="sxs-lookup"><span data-stu-id="70f73-253">Total message posts for selected period.</span></span>

  - <span data-ttu-id="70f73-254">Общее количество включенных комнат.</span><span class="sxs-lookup"><span data-stu-id="70f73-254">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="70f73-255">Пример</span><span class="sxs-lookup"><span data-stu-id="70f73-255">Example</span></span>

<span data-ttu-id="70f73-256">В следующем примере показано создание отчета об использовании за весь год 2001 и помещение отчета в Аутпутфолдер, указанный в ChatUsageReport.exe.config.</span><span class="sxs-lookup"><span data-stu-id="70f73-256">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="70f73-257">ChatUsageReport.exe.config:</span><span class="sxs-lookup"><span data-stu-id="70f73-257">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="70f73-258">счедулеадсинкфорпринЦипал</span><span class="sxs-lookup"><span data-stu-id="70f73-258">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="70f73-259">Описание</span><span class="sxs-lookup"><span data-stu-id="70f73-259">Description</span></span>

<span data-ttu-id="70f73-260">СчедулеадсинкфорпринЦипал — это скрипт Microsoft SQL Server 2012, который необходимо запускать непосредственно из SQL Server Management Studio при подключении к базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-260">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="70f73-261">Этот сценарий позволяет принудительно применять сохраняемый чат для синхронизации записей пользователя с ними из доменных служб Active Directory, а не ждать запланированного времени синхронизации.</span><span class="sxs-lookup"><span data-stu-id="70f73-261">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="70f73-262">Требования</span><span class="sxs-lookup"><span data-stu-id="70f73-262">Requirements</span></span>

<span data-ttu-id="70f73-263">Учетная запись пользователя, с помощью которой запускается сценарий, должна иметь доступ владельца к внутренней базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="70f73-263">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="70f73-264">Применение</span><span class="sxs-lookup"><span data-stu-id="70f73-264">Usage</span></span>

<span data-ttu-id="70f73-265">Ниже приведено содержимое скрипта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="70f73-265">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

