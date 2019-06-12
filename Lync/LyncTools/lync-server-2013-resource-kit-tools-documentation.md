---
title: Документация по средствам пакета ресурсов Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589285948bd9d3f82fae0ed7c7916029716514f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="1d61e-102">Документация по средствам пакета ресурсов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61e-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d61e-103">_**Тема последнего изменения:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="1d61e-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="1d61e-104">В этой статье описаны инструменты, которые входят в состав пакета ресурсов Lync Server 2013, в том числе назначение каждого из них и примеры их использования. Lync Server 2013, средства набора ресурсов помогают упростить выполнение повседневных задач для ИТ – администраторов, развертывающих Lync Server 2013 и управляющих ими.</span><span class="sxs-lookup"><span data-stu-id="1d61e-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="1d61e-105">Например, инструмент **Web Conf Data** упрощает управление данными, которые отправляют пользователи во время собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="1d61e-106">А при помощи **SEFAUtil** можно настроить переадресацию звонков делегатам и ответ на них для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d61e-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="1d61e-107">Корпорация Майкрософт рекомендует администраторам использовать эти средства для более эффективного управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="1d61e-108">Установка средств из набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="1d61e-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="1d61e-109">Чтобы установить Lync Server 2013, средства набора ресурсов, загрузите **оксрескит. msi**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="1d61e-110">Вы можете скачать установщик средств набора ресурсов из центра загрузки по адресу [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span><span class="sxs-lookup"><span data-stu-id="1d61e-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="1d61e-111">Чтобы выполнить простую установку, запустите файл **OCSResKit.msi**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="1d61e-112">MSI устанавливает все инструменты, указанные в следующем пути: **% Program Files\\% Microsoft Lync Server\\2013 рескит**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="1d61e-113">Инструменты, представляющие собой автономные исполняемые файлы, находятся непосредственно в этой папке.</span><span class="sxs-lookup"><span data-stu-id="1d61e-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="1d61e-114">Инструменты, у которых также есть файлы, находятся в своих вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="1d61e-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="1d61e-115">Поддерживаемые среды</span><span class="sxs-lookup"><span data-stu-id="1d61e-115">Supported Environments</span></span>

<span data-ttu-id="1d61e-116">Для оптимальной производительности в Lync Server 2013 вы сможете установить средства набора ресурсов в той же среде и те же спецификации, которые необходимы для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="1d61e-117">Обзор средств из набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="1d61e-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="1d61e-118">В списке ниже описаны средства, доступные в наборе ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="1d61e-119">Описание каждого инструмента, включая требования и примеры использования, описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="1d61e-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="1d61e-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="1d61e-120">ABSConfig</span></span>

  - <span data-ttu-id="1d61e-121">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="1d61e-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="1d61e-122">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="1d61e-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="1d61e-123">Счетчик парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="1d61e-123">Call Parkometer</span></span>

  - <span data-ttu-id="1d61e-124">Клеанупсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="1d61e-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="1d61e-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="1d61e-125">DBAnalyze</span></span>

  - <span data-ttu-id="1d61e-126">Импортсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="1d61e-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="1d61e-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="1d61e-127">LCSSync</span></span>

  - <span data-ttu-id="1d61e-128">Лукупусерконсоле</span><span class="sxs-lookup"><span data-stu-id="1d61e-128">LookupUserConsole</span></span>

  - <span data-ttu-id="1d61e-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="1d61e-129">MsTurnPing</span></span>

  - <span data-ttu-id="1d61e-130">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="1d61e-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="1d61e-131">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="1d61e-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="1d61e-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="1d61e-132">SEFAUtil</span></span>

  - <span data-ttu-id="1d61e-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="1d61e-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="1d61e-134">Перенос оповещений о неназначенных номерах</span><span class="sxs-lookup"><span data-stu-id="1d61e-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="1d61e-135">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="1d61e-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="1d61e-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="1d61e-136">ABSConfig</span></span>

<span data-ttu-id="1d61e-137">Средство настройки службы адресных книг (Абсконфиг) — это средство администрирования, которое помогает администраторам настраивать конфигурацию службы адресной книги в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="1d61e-138">Этот инструмент также позволяет администраторам Lync Server 2013 восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d61e-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-139">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-139">Description</span></span>

<span data-ttu-id="1d61e-140">Абсконфиг — это графическое приложение пользовательского интерфейса, которое позволяет администраторам настраивать атрибуты доменных служб Active Directory, связанные с службой адресной книги.</span><span class="sxs-lookup"><span data-stu-id="1d61e-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="1d61e-141">Основные сценарии использования этого средства:</span><span class="sxs-lookup"><span data-stu-id="1d61e-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="1d61e-142">Чтобы разрешить администраторам сопоставлять атрибуты доменных служб Active Directory с атрибутами для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="1d61e-143">позволяет администраторам указывать, что атрибут доменных служб Active Directory должен быть включен в файлы службы адресной книги или исключен из них;</span><span class="sxs-lookup"><span data-stu-id="1d61e-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="1d61e-144">позволяет администраторам восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d61e-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="1d61e-145">Средство Абсконфиг можно запустить с помощью файла Абсконфиг. exe.</span><span class="sxs-lookup"><span data-stu-id="1d61e-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="1d61e-146">Это средство откроется на вкладке " **Настройка атрибутов** ". В этой таблице есть параметры сопоставления атрибутов доменных служб Active Directory полям атрибутов для Lync Server 2013 и указания пользователей, которые нужно включить или исключить из файлов службы адресной книги на основе определенных фильтров атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="1d61e-147">Также можно настроить значение номера телефона, которое необходимо включить в файл адресной книги.</span><span class="sxs-lookup"><span data-stu-id="1d61e-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="1d61e-148">Кнопка **Восстановить значения по умолчанию** позволяет администраторам восстановить параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d61e-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="1d61e-149">Изменения из Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1d61e-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="1d61e-150">В средстве конфигурирования на Lync Server 2013 можно удалить атрибуты (строки), сняв флажок "включить" для атрибута.</span><span class="sxs-lookup"><span data-stu-id="1d61e-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="1d61e-151">Это действие аналогично удалению строки в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1d61e-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-152">Флажок Enable (включить) находится в крайнем правом столбце; чтобы увидеть столбец, возможно, потребуется прокрутить страницу вправо.</span><span class="sxs-lookup"><span data-stu-id="1d61e-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-153">Output</span></span>

<span data-ttu-id="1d61e-154">Средство ABSConfig сохраняет конфигурацию службы адресной книги в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1d61e-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-155">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-155">Purpose</span></span>

<span data-ttu-id="1d61e-156">Абсконфиг предоставляет быстрый и простой способ настройки службы 2013 в адресной книге Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-157">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="1d61e-158">Компьютер</span><span class="sxs-lookup"><span data-stu-id="1d61e-158">Computer</span></span>

<span data-ttu-id="1d61e-159">Абсконфиг можно запускать только с компьютера, подключенного к домену, на котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="1d61e-160">В случае Lync Server 2013 с корпоративным выпуском это средство может быть запущено на всех серверах переднего плана, на которых в процессе настройки включена служба адресной книги.</span><span class="sxs-lookup"><span data-stu-id="1d61e-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="1d61e-161">Сеть</span><span class="sxs-lookup"><span data-stu-id="1d61e-161">Network</span></span>

<span data-ttu-id="1d61e-162">Компьютер должен иметь возможность подключения к интерфейсному пулу и внутренней базе данных.</span><span class="sxs-lookup"><span data-stu-id="1d61e-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="1d61e-163">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="1d61e-163">Software</span></span>

<span data-ttu-id="1d61e-164">Перед запуском средства ABSConfig необходимо установить перечисленные ниже программные компоненты.</span><span class="sxs-lookup"><span data-stu-id="1d61e-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="1d61e-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61e-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="1d61e-166">Пользователи</span><span class="sxs-lookup"><span data-stu-id="1d61e-166">Users</span></span>

<span data-ttu-id="1d61e-167">Администраторы, у которых есть разрешения, необходимые для обновления развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-168">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-168">Examples</span></span>

<span data-ttu-id="1d61e-p109">Средство ABSConfig можно запустить, введя в командной строке команду **ABSConfig.exe**. Ниже показан пользовательский интерфейс средства ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p109">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="1d61e-171">![Средство абсконфиг. exe.] (images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Средство абсконфиг. exe.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-172">Заключение</span><span class="sxs-lookup"><span data-stu-id="1d61e-172">Summary</span></span>

<span data-ttu-id="1d61e-173">Средство Абсконфиг предоставляет администраторам простой и удобный инструмент для настройки службы адресной книги Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="1d61e-174">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="1d61e-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="1d61e-175">Монитор службы политики пропускной способности позволяет администраторам просматривать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1d61e-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="1d61e-176">Все настроенные службы политики пропускной способности Lync Server 2013 (проверка подлинности и ядро) в топологии</span><span class="sxs-lookup"><span data-stu-id="1d61e-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="1d61e-177">соединения, которые каждая служба устанавливает с другими службами политики пропускной способности и с пограничными серверами;</span><span class="sxs-lookup"><span data-stu-id="1d61e-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="1d61e-178">все каналы, настроенные в документе конфигурации сети, и сведения об использовании пропускной способности в реальном времени, сообщаемые каждой службой политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-179">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-179">Description</span></span>

<span data-ttu-id="1d61e-p110">Монитор службы политики пропускной способности реализован в виде приложения с графическим пользовательским интерфейсом. Чтобы запустить средство, администраторам необходимо выполнить файл PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p110">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="1d61e-p111">При запуске средства оно пытается обнаружить все службы политики пропускной способности в топологии. После начального обновления данных область в левой части окна заполняется списком служб, сгруппированным по кластерам, к которым они относятся.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p111">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="1d61e-p112">Когда администратор выбирает определенную службу политики пропускной способности, в области справа выводятся сведения о ней. Эта область имеет две основные вкладки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p112">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="1d61e-186">Вкладка Machine Info</span><span class="sxs-lookup"><span data-stu-id="1d61e-186">Machine Info Tab</span></span>

<span data-ttu-id="1d61e-187">На вкладке **Machine Info** (Сведения о компьютере) выводятся подробные сведения о выбранной службе политики пропускной способности, а также список соединений, установленных этой службой с другими службами, и их состояний.</span><span class="sxs-lookup"><span data-stu-id="1d61e-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="1d61e-188">Вкладка Topology Info</span><span class="sxs-lookup"><span data-stu-id="1d61e-188">Topology Info Tab</span></span>

<span data-ttu-id="1d61e-p113">На вкладке **Topology Info** (Сведения о топологии) показан список всех каналов, настроенных в параметрах конфигурации сети. Для каждого канала показана пропускная способность звука и видео. Кроме того, показана текущая используемая пропускная способность в Кбит/с и в процентах от общей пропускной способности. Для выделения каналов, пропускная способность которых используется почти максимально, в средстве применяется цветовая кодировка. Это позволяет администраторам быстро определять такие каналы.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p113">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-p114"> Если монитору службы политики пропускной способности не удается подключиться к какой-либо из настроенных служб политики пропускной способности, сведения на вкладках <STRONG>Machine Info</STRONG> и <STRONG>Topology Info</STRONG> не заполняются. Однако также возможна ситуация, когда средству изначально удается подключиться к службе, но затем это соединение оказывается разорванным. В таких случаях администраторы будут видеть устаревшие данные. На каждой вкладке есть метка времени <STRONG>Last Updated</STRONG> (Последнее обновление), с помощью которой администраторы могут узнать, когда в последний раз обновлялись данные для определенной службы политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p114">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated. However, it is possible that the tool might connect initially but subsequently lose its connection to the service. In such cases, administrators might see outdated information. There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-197">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-197">Output</span></span>

<span data-ttu-id="1d61e-198">Вывод данных через командную строку не используется. Данные программы выводятся в основном графическом интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-199">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-199">Purpose</span></span>

<span data-ttu-id="1d61e-p115">Монитор службы политики пропускной способности позволяет администраторам просматривать состояние каждой службы политики пропускной способности, определенной в топологии. Кроме того, администраторы могут просматривать сведения об использовании пропускной способности в реальном времени для всех каналов, определенных в документе конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p115">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-202">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-202">Requirements</span></span>

<span data-ttu-id="1d61e-203">Средство наблюдения за работой политики пропускной способности необходимо запускать на компьютере, который входит в топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-204">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-204">Summary</span></span>

<span data-ttu-id="1d61e-205">Монитор службы пропускной способности может быть ценным ресурсом для администраторов, позволяя им наблюдать за состоянием всех служб политики пропускной способности в топологии и, что еще более важно, получать сведения об использовании пропускной способности в реальном времени для каналов, определенных в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="1d61e-206">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="1d61e-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="1d61e-p116">Анализатор использования полосы пропускания — это средство, которое создает отчеты о различных аспектах использования полосы пропускания каналов глобальной сети конечными точками объединенных коммуникаций в корпоративной сети. Эти отчеты можно использовать для анализа текущей схемы использования полосы пропускания, а также при планировании емкости полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p116">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-209">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-209">Description</span></span>

<span data-ttu-id="1d61e-p117">Анализатор использования полосы пропускания реализован в виде приложения с графическим пользовательским интерфейсом. Это средство создает отчеты об использовании полосы пропускания аудиоданных в сети и помогает при планировании ресурсов. Оно также позволяет просматривать полосу пропускания, назначенную различным каналам.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p117">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-213">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-213">Output</span></span>

<span data-ttu-id="1d61e-214">Анализатор использования пропускной способности предоставляет графическое изображение полосы пропускания аудиоданных и степени ее использования для всех каналов глобальной сети, настроенных в системе.</span><span class="sxs-lookup"><span data-stu-id="1d61e-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-215">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-215">Purpose</span></span>

<span data-ttu-id="1d61e-p118">В любом развертывании системы голосовой и видеосвязи крайне важно отслеживать и анализировать тенденции использования полосы пропускания при передаче мультимедийных данных по корпоративной сети. Анализатор использования полосы пропускания позволяет администраторам решать эту задачу. Это средство предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="1d61e-p118">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network. The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that. This tool does the following:</span></span>

  - <span data-ttu-id="1d61e-219">создает отчеты по использованию звуковых каналов в сети;</span><span class="sxs-lookup"><span data-stu-id="1d61e-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="1d61e-220">позволяет более эффективно планировать емкость и распределять полосы пропускания, назначенные различным каналам.</span><span class="sxs-lookup"><span data-stu-id="1d61e-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="1d61e-221">Анализатор пропускной способности позволяет создавать следующие графические отчеты о полосе пропускания и степени ее загрузки:</span><span class="sxs-lookup"><span data-stu-id="1d61e-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="1d61e-222">для всех каналов глобальной сети в корпоративной сети;</span><span class="sxs-lookup"><span data-stu-id="1d61e-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="1d61e-223">для выбранных каналов глобальной сети;</span><span class="sxs-lookup"><span data-stu-id="1d61e-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="1d61e-224">для каналов глобальной сети, емкость которых превышена;</span><span class="sxs-lookup"><span data-stu-id="1d61e-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="1d61e-225">для каналов глобальной сети, полоса пропускания которых используется недостаточно;</span><span class="sxs-lookup"><span data-stu-id="1d61e-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="1d61e-226">для каналов глобальной сети, использование которых достигает критического уровня (то есть превышает 90 % полосы пропускания канала глобальной сети);</span><span class="sxs-lookup"><span data-stu-id="1d61e-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="1d61e-227">для каналов глобальной сети, отфильтрованных по типу: каналы между сетевыми сайтами, каналы между областями и каналы внутри сайта;</span><span class="sxs-lookup"><span data-stu-id="1d61e-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="1d61e-228">с фильтрацией по области сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="1d61e-229">Приложения</span><span class="sxs-lookup"><span data-stu-id="1d61e-229">Applications</span></span>

<span data-ttu-id="1d61e-230">Анализатор использования полосы пропускания включает следующие два приложения (средства).</span><span class="sxs-lookup"><span data-stu-id="1d61e-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="1d61e-231">**Ванлинклогколлектор. exe**   это средство позволяет пользователю вводить необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="1d61e-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="1d61e-232">**Бандвидсутилизатионанализер. xlsm**  . отчет по электронной таблице Microsoft Excel автоматически запускается программой ванлинклогколлектор. exe.</span><span class="sxs-lookup"><span data-stu-id="1d61e-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="1d61e-233">Это приложение позволяет пользователю применять фильтры к отчету, как описывается далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1d61e-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="1d61e-234">Этапы работы с анализатором использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="1d61e-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="1d61e-235">Работа с анализатором использования пропускной способности состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="1d61e-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="1d61e-236">сбор журналов, выполняемый с помощью программы WanLinkLogCollector.exe;</span><span class="sxs-lookup"><span data-stu-id="1d61e-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="1d61e-237">настройка отчетов, выполняемая с помощью электронной таблицы BandwidthUtilizationAnalyzer.xlsm.</span><span class="sxs-lookup"><span data-stu-id="1d61e-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1d61e-238">Мы настоятельно рекомендуем конечным пользователям не запускать электронную таблицу BandwidthUtilizationAnalyzer.xlsm вручную.</span><span class="sxs-lookup"><span data-stu-id="1d61e-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="1d61e-239">Запуск анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="1d61e-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="1d61e-240">Запустите файл WanLinkLogCollector.exe с помощью командной строки или проводника.</span><span class="sxs-lookup"><span data-stu-id="1d61e-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="1d61e-241">**Использование программы WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="1d61e-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="1d61e-242">Использование программы WanLinkLogCollector.exe включает три этапа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="1d61e-243">**Регистрировать временную**   шкалу обеспечивает создание отчета на временной шкале</span><span class="sxs-lookup"><span data-stu-id="1d61e-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="1d61e-244">**Указание каталогов**   файлов для предоставления сведений о расположении файлов</span><span class="sxs-lookup"><span data-stu-id="1d61e-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="1d61e-245">**Сбор журналов и запуск средства просмотра**  отчетов. выполнение команды для создания отчета</span><span class="sxs-lookup"><span data-stu-id="1d61e-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="1d61e-246">Этап 1. Регистрация временной шкалы</span><span class="sxs-lookup"><span data-stu-id="1d61e-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="1d61e-247">Регистрация временной шкалы позволяет пользователю средства указать следующие сведения, как показано на рисунке ниже. </span><span class="sxs-lookup"><span data-stu-id="1d61e-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="1d61e-248">**Дата начала**. Это начальная дата временной шкалы, для которой нужно создать отчет, например 1 августа 2010 г.</span><span class="sxs-lookup"><span data-stu-id="1d61e-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="1d61e-249">**Дата окончания**. Это конечная дата временной шкалы, для которой нужно создать отчет, например 30 сентября 2010 г.</span><span class="sxs-lookup"><span data-stu-id="1d61e-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="1d61e-250">![Даты начала и окончания в использовании пропускной способности] (images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Даты начала и окончания в использовании пропускной способности")</span><span class="sxs-lookup"><span data-stu-id="1d61e-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="1d61e-251">Этап 2. Указание каталогов файлов</span><span class="sxs-lookup"><span data-stu-id="1d61e-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="1d61e-252">Пользователь может указать следующие каталоги файлов, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="1d61e-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="1d61e-253">**Расположение файлов журнала сервера** Расположение папки, в которой хранятся журналы сервера политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="1d61e-254">Как правило, это \<филесервер\>\\\<выбора\>\\аппсерверфилес\\PDP.</span><span class="sxs-lookup"><span data-stu-id="1d61e-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="1d61e-255">**Место хранения временных файлов** Временное расположение файлов, в котором хранятся промежуточные файлы, при создании отчета.</span><span class="sxs-lookup"><span data-stu-id="1d61e-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="1d61e-256">![Каталоги файлов в анал использования пропускной способности] (images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Каталоги файлов в анал использования пропускной способности")</span><span class="sxs-lookup"><span data-stu-id="1d61e-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-257">Пользователю средства необходимо предоставить достаточные права на доступ к файлам журналов сервера и папке хранения временных файлов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="1d61e-258">Этап 3. Сбор журналов и запуск средства просмотра отчетов</span><span class="sxs-lookup"><span data-stu-id="1d61e-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="1d61e-p121">Чтобы выполнить сбор журналов и запустить средство просмотра отчетов, нажмите кнопку **Execute** (Выполнить), как показано ниже. На этом этапе собираются необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p121">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

<span data-ttu-id="1d61e-261">![Сбор данных в анали использования пропускной способности] (images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Сбор данных в анали использования пропускной способности")</span><span class="sxs-lookup"><span data-stu-id="1d61e-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="1d61e-262">Если проверка входных данных прошла успешно, выводится показанное ниже сообщение.</span><span class="sxs-lookup"><span data-stu-id="1d61e-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="1d61e-263">![Регистрация собранных уведомлений в утили пропускной способности] (images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Регистрация собранных уведомлений в утили пропускной способности")</span><span class="sxs-lookup"><span data-stu-id="1d61e-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="1d61e-p122">Нажмите кнопку **ОК**. Автоматически откроется электронная таблица BandwidthUtilizationAnalyzer.xlsm. Следуйте инструкциям в окне сообщения. Подробные сведения см. в следующем разделе, **Использование таблицы BandwidthUtilizationAnalyzer.xlsm**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p122">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="1d61e-268">**Использование таблицы BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="1d61e-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="1d61e-269">Когда таблица BandwidthUtilizationAnalyzer.xlsm автоматически откроется, нажмите кнопку **Refresh** (Обновить), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="1d61e-270">![Бандвидсутилизатионанализер. xlsm] (images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "Бандвидсутилизатионанализер. xlsm")</span><span class="sxs-lookup"><span data-stu-id="1d61e-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="1d61e-271">Когда откроется папка с файлами, выберите файл consolidated.csv в папке, указанной в окне сообщения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="1d61e-272">Оно также показывает место в формате **C:\\Temp**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="1d61e-273">![Открытие папки в бандвидсутилизатионанализер.] (images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Открытие папки в бандвидсутилизатионанализер.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="1d61e-274">Нажмите кнопку **Import** (Импорт).</span><span class="sxs-lookup"><span data-stu-id="1d61e-274">Click **Import**.</span></span>

4.  <span data-ttu-id="1d61e-p124">Графический отчет будет создан автоматически. Он станет доступен, когда исчезнет указатель выполнения операции в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p124">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="1d61e-277">![Применение фильтров в представлении отчета.] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Применение фильтров в представлении отчета.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="1d61e-278">Применение фильтров к представлению отчета</span><span class="sxs-lookup"><span data-stu-id="1d61e-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="1d61e-279">Далее описываются фильтры, которые можно применить к представлению отчета и которые показаны ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="1d61e-280">![Применение фильтров в представлении отчета.] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Применение фильтров в представлении отчета.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="1d61e-281">**Name** (Имя). Фильтрация по каналам глобальной сети (фильтр находится в правой части графика). Префикс означает следующие типы каналов (см. вертикальное (синее) поле):</span><span class="sxs-lookup"><span data-stu-id="1d61e-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="1d61e-282">**S (Site)** — канал глобальной сети между сетевым сайтом и областью сети;</span><span class="sxs-lookup"><span data-stu-id="1d61e-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="1d61e-283">**IS (Inter-Site)** — канал глобальной сети между двумя сетевыми сайтами;</span><span class="sxs-lookup"><span data-stu-id="1d61e-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="1d61e-284">**R (Inter-Region)** — канал глобальной сети между двумя областями сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="1d61e-285">**Exceeded limit** (Превышение предела). Фильтрация каналов глобальной сети, использование полосы пропускания которых превышает доступные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="1d61e-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="1d61e-286">**Critical levels** (Критические уровни). Фильтрация каналов глобальной сети, использование полосы пропускания которых достигло 90 % или более от максимального значения.</span><span class="sxs-lookup"><span data-stu-id="1d61e-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="1d61e-287">**Under-utilized** (Недостаточное использование). Фильтрация каналов глобальной сети, использование полосы пропускания которых составляет менее 25 % от максимального.</span><span class="sxs-lookup"><span data-stu-id="1d61e-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="1d61e-288">**Link type** (Тип канала). Фильтрация по следующим типам каналов глобальной сети:</span><span class="sxs-lookup"><span data-stu-id="1d61e-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="1d61e-289">**Network site** (Сетевой сайт);</span><span class="sxs-lookup"><span data-stu-id="1d61e-289">**Network site** type</span></span>
    
      - <span data-ttu-id="1d61e-290">**Inter-site** (Между сайтами);</span><span class="sxs-lookup"><span data-stu-id="1d61e-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="1d61e-291">**Inter-Region link**(Канал между областями).</span><span class="sxs-lookup"><span data-stu-id="1d61e-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="1d61e-292">**Region** (Область). Фильтрация по области сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-292">**Region** Filter by network region</span></span>

<span data-ttu-id="1d61e-293">На следующих рисунках показаны ранее описанные фильтры.</span><span class="sxs-lookup"><span data-stu-id="1d61e-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="1d61e-p125">Примените фильтр **Name**. Выберите список каналов, которые нужно показать на графике.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p125">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="1d61e-296">![Фильтрация по имени в бандвидсутилизатионанализер.] (images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Фильтрация по имени в бандвидсутилизатионанализер.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="1d61e-297">Примените фильтр **Exceeded limit**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="1d61e-298">Установите флажок **True**, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="1d61e-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="1d61e-299">![Фильтрация по превышению предела.] (images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Фильтрация по превышению предела.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="1d61e-300">Примените фильтр **Critical levels**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="1d61e-301">Установите флажок **True**, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="1d61e-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="1d61e-302">![Фильтрация по критическим уровням.] (images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Фильтрация по критическим уровням.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="1d61e-303">Примените фильтр **Under utilized**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="1d61e-304">Установите флажок **True**, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="1d61e-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="1d61e-305">![Фильтрация по] заданному принципу. (images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Фильтрация по") заданному принципу.</span><span class="sxs-lookup"><span data-stu-id="1d61e-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="1d61e-306">Примените фильтр **Link Type**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-306">Filter by **Link Type**.</span></span> <span data-ttu-id="1d61e-307">Выберите один или несколько типов каналов, которые нужно показать.</span><span class="sxs-lookup"><span data-stu-id="1d61e-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="1d61e-308">![Фильтрация по типу связи.] (images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Фильтрация по типу связи.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="1d61e-309">Примените фильтр **Region**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-309">Filter by **Region**.</span></span> <span data-ttu-id="1d61e-310">Выберите список областей, каналы которых нужно показать.</span><span class="sxs-lookup"><span data-stu-id="1d61e-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="1d61e-311">![Фильтрация по регионам.] (images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Фильтрация по регионам.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-312">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-312">Requirements</span></span>

  - <span data-ttu-id="1d61e-313">Платформа .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="1d61e-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="1d61e-314">Microsoft Excel 2010 или Excel 2007</span><span class="sxs-lookup"><span data-stu-id="1d61e-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-315">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-315">Summary</span></span>

<span data-ttu-id="1d61e-p131">Анализатор использования полосы пропускания предназначен для графического представления данных об использовании полосы пропускания звуковых каналов для трафика объединенных коммуникаций в сети. Это средство также можно использовать для создания отчетов об использовании полосы пропускания видеоканалов в сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p131">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="1d61e-318">Счетчик парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="1d61e-318">Call Parkometer</span></span>

<span data-ttu-id="1d61e-319">Счетчик парковки вызовов — это программа командной строки, облегчающая доступ к базе данных орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-320">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-320">Description</span></span>

<span data-ttu-id="1d61e-321">Счетчик парковки вызовов — это средство для отслеживания вызовов, находящихся в состоянии парковки на данный момент.</span><span class="sxs-lookup"><span data-stu-id="1d61e-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="1d61e-322">Оно также собирает статистику по орбитам и использованию сервера парковки вызовов (CPS).</span><span class="sxs-lookup"><span data-stu-id="1d61e-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="1d61e-323">Это средство командной строки предоставляет доступ для чтения и записи к базе данных SQL Server орбиты на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d61e-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="1d61e-p133">Все параметры являются взаимоисключающими. Синтаксис командной строки имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="1d61e-p133">All options are mutually exclusive. Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="1d61e-326">
            параметр \*\*–o\*\* выводит список всех диапазонов орбиты, настроенных для этого пула;</span><span class="sxs-lookup"><span data-stu-id="1d61e-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="1d61e-p134">
            параметр \*\*–n\*\* выводит список всех орбит, используемых в настоящее время в этом пуле; отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1d61e-p134">**–n** parameter—lists all currently used orbits in this pool. The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="1d61e-329">универсальный код ресурса (URI) протокола SIP паркуемого и паркующего;</span><span class="sxs-lookup"><span data-stu-id="1d61e-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="1d61e-330">имя узла сервера парковки вызовов, на котором паркуется вызов;</span><span class="sxs-lookup"><span data-stu-id="1d61e-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="1d61e-331">метка времени парковки вызова;</span><span class="sxs-lookup"><span data-stu-id="1d61e-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="1d61e-332">
            параметр \*\*–f\*\* выводит текущее число свободных орбит в пуле;</span><span class="sxs-lookup"><span data-stu-id="1d61e-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="1d61e-333">**параметр – \<r\> n** — список всех \<абонентов, на которые вы приприпарковани\> последние звонки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="1d61e-334">Отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1d61e-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="1d61e-335">URI SIP паркуемого;</span><span class="sxs-lookup"><span data-stu-id="1d61e-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="1d61e-336">URI SIP паркующего;</span><span class="sxs-lookup"><span data-stu-id="1d61e-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="1d61e-337">имя узла сервера, на котором был припаркован вызов;</span><span class="sxs-lookup"><span data-stu-id="1d61e-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="1d61e-338">метка времени извлечения или пропуска вызова;</span><span class="sxs-lookup"><span data-stu-id="1d61e-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="1d61e-339">\*\*-t\<n\> \*\* — тестирование параметров, резервирование орбиты в базе данных для отображения случайного количества назначенных номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="1d61e-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-340">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-340">Output</span></span>

<span data-ttu-id="1d61e-341">В зависимости от входных параметров, указанных в командной строке, счетчик парковки вызовов отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="1d61e-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="1d61e-342">все диапазоны орбиты, настроенные для этого пула;</span><span class="sxs-lookup"><span data-stu-id="1d61e-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="1d61e-343">вызовы, припаркованные в настоящее время;</span><span class="sxs-lookup"><span data-stu-id="1d61e-343">Currently parked calls</span></span>

  - <span data-ttu-id="1d61e-344">число свободных (доступных) орбит;</span><span class="sxs-lookup"><span data-stu-id="1d61e-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="1d61e-345">недавно припаркованные вызовы;</span><span class="sxs-lookup"><span data-stu-id="1d61e-345">Recently parked calls</span></span>

  - <span data-ttu-id="1d61e-346">зарезервированные орбиты для проверки универсальных и случайных значений орбиты.</span><span class="sxs-lookup"><span data-stu-id="1d61e-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-347">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-347">Purpose</span></span>

<span data-ttu-id="1d61e-p136">Средство CPS предназначено для предоставления доступа к базе данных CPS из командной строки. Администратор может просматривать сведения об использовании CPS и определять число орбит, назначенных пулу.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p136">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-350">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-350">Requirements</span></span>

<span data-ttu-id="1d61e-351">Если это средство запускается на компьютере с сервером парковки вызовов, то дополнительные требования не предъявляются.</span><span class="sxs-lookup"><span data-stu-id="1d61e-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="1d61e-352">Если средство запущено на удаленном компьютере, база данных SQL Server, используемая в Lync Server 2013, должна быть настроена на разрешение удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="1d61e-353">Чтобы подключиться к серверу SQL Server, необходимо настроить вызов Паркометер с помощью строки подключения к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="1d61e-354">Эта строка подключения к базе данных SQL Server определена в файле конфигурации **паркометер. exe. config**. Он должен находиться в той же папке, где находится файл паркометер. exe.</span><span class="sxs-lookup"><span data-stu-id="1d61e-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="1d61e-355">Ниже приведен пример XML-файла паркометер. exe. config. Параметры, которые необходимо настроить, — это имя пользователя (например, администратор\\mydomain), пароль (например, MOyParoL) и имя узла (например, MyServer).</span><span class="sxs-lookup"><span data-stu-id="1d61e-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-356">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-356">Examples</span></span>

<span data-ttu-id="1d61e-357">Развернутые диапазоны орбиты: параметр –o выводит список всех диапазонов орбиты, настроенных для этого пула, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="1d61e-358">![Диапазоны на орбите в вызове паркометер.] (images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Диапазоны на орбите в вызове паркометер.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="1d61e-359">Текущие припаркованные вызовы: параметр –n выводит список всех орбит, используемых в настоящее время в этом пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="1d61e-360">![В настоящее время звонки в Паркометер вызываются в звонках.] (images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "В настоящее время звонки в Паркометер вызываются в звонках.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="1d61e-361">Число свободных орбит: параметр –f выводит текущее число свободных орбит в пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="1d61e-362">![Бесплатные орбиты в вызове паркометер.] (images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Бесплатные орбиты в вызове паркометер.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="1d61e-363">Недавно припаркованные звонки: в параметре \<–\> r n указаны \<n\> -е последние звонки, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="1d61e-364">![Недавно припаркованные звонки в вызове паркометер.] (images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Недавно припаркованные звонки в вызове паркометер.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="1d61e-365">Проверка резервирования на орбите: параметр \<–\> t n проверяет, как показано на странице базы данных.</span><span class="sxs-lookup"><span data-stu-id="1d61e-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="1d61e-366">![Проверка резервирования на орбите в вызове паркометер.] (images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Проверка резервирования на орбите в вызове паркометер.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-367">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-367">Summary</span></span>

<span data-ttu-id="1d61e-368">Счетчик парковки вызовов — это средство командной строки, предоставляющее подробные сведения о сервере парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="1d61e-369">Клеанупсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="1d61e-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="1d61e-370">Средство Клеанупсторажесервицедата Resource Kit позволяет удалять потерянные данные из базы данных, используемой службой хранилища Lync Server (Лисс).</span><span class="sxs-lookup"><span data-stu-id="1d61e-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="1d61e-371">Одной из функций службы хранилища является буферизация связи между Lync Server и разными конечными точками хранилища данных, например SQL Server и Exchange.</span><span class="sxs-lookup"><span data-stu-id="1d61e-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-372">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-372">Description</span></span>

<span data-ttu-id="1d61e-373">Для поддержки высокой доступности Лисс принимает и сохраняет копии данных на нескольких серверах переднего плана в пуле временно и удаляет эти данные после того, как они были доставлены в последнее долговременное хранилище.</span><span class="sxs-lookup"><span data-stu-id="1d61e-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="1d61e-374">Существуют нестандартные ситуации, которые могут возникнуть в обычном режиме, когда сервер может аварийно завершить работу или испытывать проблемы с обработкой, и некоторые данные могут не быть очищены должным образом.</span><span class="sxs-lookup"><span data-stu-id="1d61e-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="1d61e-375">Эти данные являются безобидными, но потребляют ресурсы с ограниченными возможностями обработки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="1d61e-376">Многие из обычных необходимых средств обслуживания данных автоматизированы, но это средство позволяет безопасно идентифицировать и удалять такие потерянные данные, если автоматическое удаление невозможно.</span><span class="sxs-lookup"><span data-stu-id="1d61e-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="1d61e-377">Использование этого средства показывается, когда инициируется оповещение System Center Operations Manager (SCOM), которое попросит администратора удалить ненужные данные из локальной базы данных Лисс в пуле.</span><span class="sxs-lookup"><span data-stu-id="1d61e-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="1d61e-378">В журнале событий на стороне переднего плана появится соответствующее событие, которое инициировало оповещение.</span><span class="sxs-lookup"><span data-stu-id="1d61e-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="1d61e-379">Сведения о событии содержат сведения о количестве потерянных данных, содержащихся в интерфейсе, и инициируется, когда эти данные превышают пороговые значения, которые предварительно определяются</span><span class="sxs-lookup"><span data-stu-id="1d61e-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-380">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-380">Requirements</span></span>

<span data-ttu-id="1d61e-381">Установите пакет инструментов Lync Server 2013, набор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="1d61e-382">Средство запускается на компьютерах, подключенных к домену, на которых установлены сервер Lync Server и управляющая оболочка Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="1d61e-383">Средство использует командлет из командной консоли для идентификации всех серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="1d61e-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="1d61e-384">Во-вторых, средство должно выполняться с компьютера в пуле, на котором установлена база данных **ртклокал** .</span><span class="sxs-lookup"><span data-stu-id="1d61e-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="1d61e-385">Эта база данных используется средством Клеанупсторажесервицедата для получения сведений о соединении, необходимых для связи со службой маршрутизации Lync Server. Наконец, учетная запись или учетные данные, вызывающие этот инструмент, должны иметь разрешение на чтение и запись в общей папке, к которой они записывают журнал вывода. Кроме того, этот инструмент зависит от пула, который находится в стабильном состоянии.</span><span class="sxs-lookup"><span data-stu-id="1d61e-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="1d61e-386">По сути, это означает, что каждый сервер переднего плана должен быть готов к работе, и каждая группа маршрутизации должна иметь полный набор 1 основных серверов переднего плана и 2-е-вспомогательного интерфейса s. ерверс.</span><span class="sxs-lookup"><span data-stu-id="1d61e-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-387">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-387">Examples</span></span>

<span data-ttu-id="1d61e-388">C:\\Program Files\\Microsoft Lync Server\\2013\\рескит\> сторажесервице импортсторажесервицедата. exe</span><span class="sxs-lookup"><span data-stu-id="1d61e-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="1d61e-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="1d61e-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-390">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-390">Description</span></span>

<span data-ttu-id="1d61e-391">Дбанализе — это средство командной строки, позволяющее администраторам собирать отчеты анализа о базах данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="1d61e-392">Средство DBAnalyze имеет следующие режимы: диагностика, пользовательские данные, конференция, узлы MCU и фрагментация дисков.</span><span class="sxs-lookup"><span data-stu-id="1d61e-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="1d61e-393">**Диагностический режим**   : создание отчета, который содержит сведения о таблицах (число записей, фрагментация, размер данных и размер индекса), размерах файлов данных и журналов, время последней архивации и связь между серверами, на которых запущены Microsoft. Office Communications Server, среднее количество разрешений, контакты, контейнеры, подписки, публикации, конечные точки на одного пользователя, неверно подключенные пользователи, пользователи, которые не могут маршрутизироваться, среднее количество конференций, упорядоченных на одного пользователя, запланированное Конференции, активные Конференции и версия базы данных.</span><span class="sxs-lookup"><span data-stu-id="1d61e-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d61e-394">Запуск средства в режиме диагностики может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="1d61e-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="1d61e-395">**Режим данных пользователя**  Отчеты о контактах, контейнерах, подписках, публикациях, разрешениях и контактных данных для определенного пользователя или пользователей, которые имеют этого пользователя в списках контактов и разрешений.</span><span class="sxs-lookup"><span data-stu-id="1d61e-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="1d61e-396">Этот режим также предоставляет сводные данные по конференциям, которые организовал пользователь или на которые он приглашен.</span><span class="sxs-lookup"><span data-stu-id="1d61e-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="1d61e-397">**Режим конференций с**   подробными данными о конкретной конференции, включая сведения о времени расписания для Конференции, список "пригласить", список типов мультимедиа, разрешенных для Конференции, активный мкус (единицы управления MultiPoint), активный Список участников и состояние сигналов каждого участника.</span><span class="sxs-lookup"><span data-stu-id="1d61e-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="1d61e-398">**Декодирование идентификатора**  собрания декодирует идентификационный номер, указанный в параметре **/пстнид** , но не подключается к серверу для получения подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="1d61e-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="1d61e-399">\*\*\*\*   Разрешите декодировать конференцию, которая указана в параметре " **/пстнид** ", и выводит сведения о конференции, обозначенные идентификатором.</span><span class="sxs-lookup"><span data-stu-id="1d61e-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="1d61e-400">**Режим мкус:**  идентификатор, тип носителя, URL-адрес, состояние пульса, нагрузка Конференции и нагрузка участника для каждой MCU в пуле.</span><span class="sxs-lookup"><span data-stu-id="1d61e-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="1d61e-401">**В режиме**  фрагментации диска отображается состояние фрагментации всех дисков.</span><span class="sxs-lookup"><span data-stu-id="1d61e-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="1d61e-p143">Администраторы могут использовать это средство для диагностики различных проблем или при планировании емкости. Например, если большинство пользователей, размещенных на сервере А, выбрали в качестве контактов пользователей, размещенных на сервере Б, администратор может перенести пользователей с сервера А на сервер Б, чтобы уменьшить объем трафика между серверами.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p143">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-404">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-404">Output</span></span>

<span data-ttu-id="1d61e-405">Это средство выводит предопределенные отчеты о базе данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="1d61e-406">**Путь:** % ProgramFiles%\\Microsoft Lync Server 2013\\рескит</span><span class="sxs-lookup"><span data-stu-id="1d61e-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-407">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-407">Purpose</span></span>

<span data-ttu-id="1d61e-408">Чтобы установить Дбанализе. exe, скопируйте его в локальную папку, а затем запустите средство.</span><span class="sxs-lookup"><span data-stu-id="1d61e-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="1d61e-409">Чтобы воспользоваться средством, выполните в командной строке следующую команду:`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="1d61e-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="1d61e-410">Ниже приведены описания параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="1d61e-411">![Параметры командной строки для дбанализе. exe.] (images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Параметры командной строки для дбанализе. exe.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-412">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-412">Requirements</span></span>

<span data-ttu-id="1d61e-413">**Компьютера** Дбанализе можно запускать только с компьютера, подключенного к домену, на котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="1d61e-414">**Сеть**. Компьютер должен иметь возможность подключения к внутренней базе данных.</span><span class="sxs-lookup"><span data-stu-id="1d61e-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="1d61e-415">**Software (программное обеспечение** ) Перед запуском Дбанализе необходимо установить компоненты программного обеспечения Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="1d61e-416">**Пользователи** В приведенной ниже таблице указаны администраторы, у которых есть необходимые разрешения на доступ к базам данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="1d61e-417">![Таблица разрешений для дбанализе. exe.] (images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Таблица разрешений для дбанализе. exe.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-418">Для режима <STRONG>/report:disk</STRONG> необходима учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="1d61e-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-419">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-419">Examples</span></span>

<span data-ttu-id="1d61e-420">Ниже приведены примеры допустимых команд Dbanalyze.exe.</span><span class="sxs-lookup"><span data-stu-id="1d61e-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-421">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-421">Summary</span></span>

<span data-ttu-id="1d61e-422">Дбанализер позволяет администраторам быстро и легко анализировать базы данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="1d61e-423">Импортсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="1d61e-423">ImportStorageServiceData</span></span>

<span data-ttu-id="1d61e-424">Средство ImportStorageServiceData из набора ресурсов позволяет повторно импортировать данные очереди и конечных точек, записанные на диск из службы хранилища (LYSS), обратно в эту службу.</span><span class="sxs-lookup"><span data-stu-id="1d61e-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-425">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-425">Description</span></span>

<span data-ttu-id="1d61e-426">Данные могут записываться на диск из службы хранилища автоматически (периодически) в зависимости от состояния элемента очереди или размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="1d61e-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="1d61e-427">Это может происходить в результате вызова командлета отработки отказа пула вручную или вызова командлета StorageServiceFullFlush (командлетом отработки отказа пула).</span><span class="sxs-lookup"><span data-stu-id="1d61e-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="1d61e-428">Обратите внимание, что в противном случае данные должны быть повторно импортированы, если какой-либо размер базы данных службы хранилища (Лисс) на передних координатах выходит за границы обычного уровня, так как это может привести к тому, что все данные будут экспортированы. Кроме того, любые проблемы, которые могут привести к ошибкам увеличения размера очереди обслуживания хранилища, должны быть решены (например, ошибки конечной точки Exchange, проблемы с сетью или другие проблемы).</span><span class="sxs-lookup"><span data-stu-id="1d61e-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="1d61e-429">**Сценарий 1:** во время отработки отказа пула файлы могут быть удалены из службы хранилища для каждого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1d61e-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="1d61e-430">После завершения отработки отказа необходимо выполнить повторное импорт данных с помощью инструмента.</span><span class="sxs-lookup"><span data-stu-id="1d61e-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="1d61e-431">**Сценарий 2**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="1d61e-432">Данные записываются на диск автоматически каждый день или при превышении базой данных службы хранилища определенного порогового значения размера (например заполненность на 60, 80 или 90 %).</span><span class="sxs-lookup"><span data-stu-id="1d61e-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="1d61e-433">В описанной выше ситуации, если пакет SCOM для мониторинга не развернут, в службе хранилища Lync Server есть события, связанные с сбросом данных из службы хранилища.</span><span class="sxs-lookup"><span data-stu-id="1d61e-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="1d61e-434">Если в описанной выше ситуации не развернут пакет мониторинга SCOM, создаются события службы хранилища skype16_server_short, связанные с записью на диск данных из нее, а именно события с идентификаторами 32075 (началась операция полной записи на диск), 32076 (полная запись на диск завершена), 32082 (началась запись на диск на уровне обслуживания), 32083 (запись на диск на уровне обслуживания завершена) и 32089 (запись на диск выполнена в связи с заполнением базы данных).</span><span class="sxs-lookup"><span data-stu-id="1d61e-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="1d61e-435">Обратите внимание, что эти идентификаторы событий соответствуют окончательному первоначальному выпуску (RTM).</span><span class="sxs-lookup"><span data-stu-id="1d61e-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="1d61e-436">Если администратор видит эти события, это означает, что файлы были удалены. Эти данные следует регулярно импортировать с помощью этого инструмента, например один раз в неделю.</span><span class="sxs-lookup"><span data-stu-id="1d61e-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="1d61e-437">Для выпусков интерактивных служб, если вы развернули пакет SCOM для мониторинга работоспособности для Lync Server, вы можете создать новые оповещения, которые попросите администратора повторно импортировать очищенные данные обратно в службу хранилища.</span><span class="sxs-lookup"><span data-stu-id="1d61e-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="1d61e-438">На сервере переднего плана, на котором инициировано оповещение, появится соответствующее событие в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="1d61e-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="1d61e-439">Событие выдаст описание родительского пути, под которым находятся очищенные файлы данных, а также количество файлов, которые удовлетворяют условиям оповещения.</span><span class="sxs-lookup"><span data-stu-id="1d61e-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="1d61e-440">Критерий оповещения состоит в том, что для определенного родительского пути есть X или более файлов, которые имеют по крайней мере по меньшей мере Y дн. (где X и Y являются предварительно заданными в Сторажесервице, но их можно переопределить, изменив АППКОНФИГ файл). Ниже приведены два примера событий, которые могут инициировать оповещение о работоспособности, а также отличия от их родительского пути.</span><span class="sxs-lookup"><span data-stu-id="1d61e-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="1d61e-441">Один из возможных вариантов — это файловый общий доступ к веб-службе, а другая возможность — локальный каталог данных приложения для каждого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1d61e-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="1d61e-442">(например, c:\\програмдата\\Microsoft\\Lync Server\\сторажесервице).</span><span class="sxs-lookup"><span data-stu-id="1d61e-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="1d61e-443">После этого администратор запустит это средство рескит.</span><span class="sxs-lookup"><span data-stu-id="1d61e-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="1d61e-444">Это средство повышает загрузку ЦП и интенсивность операций ввода-вывода на сервере переднего плана, на котором оно запущено, а также на других серверах переднего плана, если данные не принадлежат серверу, на котором выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="1d61e-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="1d61e-445">Мы не рекомендуем запускать это средство, когда загрузка ЦП и интенсивность операций ввода-вывода на серверах переднего плана высоки (например, в часы пиковой нагрузки).</span><span class="sxs-lookup"><span data-stu-id="1d61e-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="1d61e-446">Во-вторых, на импорт одного файла данных средству может потребоваться 2–3 минуты.</span><span class="sxs-lookup"><span data-stu-id="1d61e-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="1d61e-447">Помните о том, как выполняется оценка продолжительности работы средства. Подробный файл журнала, созданный средством, будет использоваться по умолчанию в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="1d61e-448">Удалите его, если он не содержит ошибок, так как его размер может составлять десятки мегабайт и более.</span><span class="sxs-lookup"><span data-stu-id="1d61e-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="1d61e-449">![Пример событий в журнале событий сервера хранилища.] (images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Пример событий в журнале событий сервера хранилища.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-450">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-450">Requirements</span></span>

<span data-ttu-id="1d61e-451">Установите пакет инструментов Lync Server 2013, набор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="1d61e-452">Это средство запускается на компьютерах, подключенных к домену, на которых установлены сервер Lync Server и консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="1d61e-453">Средство использует командлет из командной консоли для идентификации всех серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="1d61e-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="1d61e-454">Во-вторых, средство должно выполняться с компьютера в пуле, на котором установлена база данных **ртклокал** .</span><span class="sxs-lookup"><span data-stu-id="1d61e-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="1d61e-455">Эта база данных используется средством для извлечения расположения файла сетевой службы WebService для пула. Кроме того, прежде чем использовать инструмент, каждый сервер переднего плана должен сначала включить удаленное взаимодействие Windows PowerShell с помощью функции **Enable-псремотинг** на каждом сервере переднего плана, а также на компьютере, с которого запускается средство.</span><span class="sxs-lookup"><span data-stu-id="1d61e-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="1d61e-456">В противном случае удаленные команды Windows PowerShell из этого средства завершатся сбоем.</span><span class="sxs-lookup"><span data-stu-id="1d61e-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="1d61e-457">Удаленное взаимодействие Windows PowerShell может быть отключено на всех серверах переднего плана в пуле после его завершения.</span><span class="sxs-lookup"><span data-stu-id="1d61e-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="1d61e-458">Наконец, учетная запись или учетные данные, вызывающие этот инструмент, должны иметь разрешение на чтение и запись для общего файлового файла WebService для пула, на котором они выполняются.</span><span class="sxs-lookup"><span data-stu-id="1d61e-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="1d61e-459">В противном случае средство завершится сбоем с ошибками разрешений на ввод-вывод.</span><span class="sxs-lookup"><span data-stu-id="1d61e-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-460">В Windows Server 2012 удаленное взаимодействие Windows PowerShell включено по умолчанию, но не в операционной системе Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1d61e-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-461">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-461">Examples</span></span>

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="1d61e-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="1d61e-462">LCSSync</span></span>

<span data-ttu-id="1d61e-463">Средство Лкссинк помогает развертывать коммуникационные программы для Lync Server 2013 в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="1d61e-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="1d61e-464">Это средство используется для синхронизации пользователей и групп из разных лесов пользователей в качестве объекта-контакта доменных служб Active Directory с основным лесом, в котором установлен сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-465">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-465">Description</span></span>

<span data-ttu-id="1d61e-466">Лкссинк использует синхронизированные объекты контакта доменных служб Active Directory в центральном лесе, чтобы включить пользователей для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="1d61e-467">Для предоставления единого входа основная учетная запись пользователя должна быть сопоставлена с объектом контакта доменных служб Active Directory в центральном лесе Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="1d61e-468">Это средство помогает выполнить такое сопоставление.</span><span class="sxs-lookup"><span data-stu-id="1d61e-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="1d61e-469">Оно предоставляет шаблоны для создания агентов управления на сервере Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-470">Заключение</span><span class="sxs-lookup"><span data-stu-id="1d61e-470">Summary</span></span>

<span data-ttu-id="1d61e-471">Средство Лкссинк помогает развернуть Lync Server в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="1d61e-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="1d61e-472">Лукупусерконсоле</span><span class="sxs-lookup"><span data-stu-id="1d61e-472">LookupUserConsole</span></span>

<span data-ttu-id="1d61e-473">Средство Лукупусерконсоле выводит сведения о маршрутизации для конкретных пользователей на сервере Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="1d61e-474">Эти сведения могут быть полезны специалистам службы поддержки Майкрософт при диагностике проблем с развертыванием и маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="1d61e-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-475">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-475">Description</span></span>

<span data-ttu-id="1d61e-476">При запуске Лукупусерконсоле. exe откроется Командная строка, которая принимает адреса SIP и пытается отобразить внутренние данные маршрутизации Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="1d61e-477">Чтобы выйти из средства LookupUserConsole, введите команду **exit**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-478">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-478">Requirements</span></span>

<span data-ttu-id="1d61e-479">Установите пакет инструментов Lync Server 2013, набор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="1d61e-480">Средство запускается на компьютерах, подключенных к домену, на которых установлено приложение Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-481">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-481">Examples</span></span>

<span data-ttu-id="1d61e-482">C:\\Program Files\\Microsoft Lync Server\\2013\>рескит лукупусерконсоле. exe</span><span class="sxs-lookup"><span data-stu-id="1d61e-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="1d61e-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="1d61e-483">MsTurnPing</span></span>

<span data-ttu-id="1d61e-484">Средство Мстурнпинг позволяет администратору коммуникационного программного обеспечения Microsoft Lync Server 2013 проверять состояние серверов, на которых работают службы голосовой и видеосвязи, а также серверы, на которых работает политика пропускной способности. Службы в топологии.</span><span class="sxs-lookup"><span data-stu-id="1d61e-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-485">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-485">Description</span></span>

<span data-ttu-id="1d61e-486">Средство Мстурнпинг позволяет администратору коммуникационного программного обеспечения Lync Server 2013 проверять состояние серверов, использующих голосовые и видеозвонки, службы проверки подлинности аудио-и видеосвязи, а также серверы, на которых работают службы политики пропускной способности. Topology.</span><span class="sxs-lookup"><span data-stu-id="1d61e-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="1d61e-487">Средство позволяет администратору выполнять перечисленные ниже проверки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="1d61e-488">Проверка пограничных серверов аудио- и видеоданных — средство тестирует все пограничные серверы аудио- и видеоданных в топологии, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1d61e-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="1d61e-489">Проверка того, что служба проверки подлинности в Lync Server Audio/видео запущена и может выпустить необходимые учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1d61e-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="1d61e-490">Проверка того, что служба внешнего и видеоedge Lync Server запущена и может успешно выделять ресурсы на внешнем Edge.</span><span class="sxs-lookup"><span data-stu-id="1d61e-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="1d61e-491">Проверка службы политики пропускной способности — средство тестирует все серверы в топологии, на которых запущены службы политики пропускной способности, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1d61e-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="1d61e-492">Проверка того, что служба политики пропускной способности Lync Server (проверка подлинности) запущена и может выпустить правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="1d61e-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="1d61e-493">Проверка того, что служба политики пропускной способности сервера Lync Server (ядро) запущена, и может успешно выполнить проверку пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="1d61e-494">Это средство необходимо запускать на компьютере, который входит в топологию и на котором установлено локальное хранилище. </span><span class="sxs-lookup"><span data-stu-id="1d61e-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-495">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-495">Output</span></span>

<span data-ttu-id="1d61e-496">Средство выводит результаты каждой операции.</span><span class="sxs-lookup"><span data-stu-id="1d61e-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="1d61e-497">Если выполняется тест **AudioVideoEdgeServer**, выходные данные включают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1d61e-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="1d61e-498">Результаты тестирования компьютеров, предоставляющих службе проверки подлинности в Lync Server Audio/видео в топологии</span><span class="sxs-lookup"><span data-stu-id="1d61e-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="1d61e-499">Результаты тестирования компьютеров, которые предоставляют службу для работы с аудио-и видеоedge Lync Server в топологии</span><span class="sxs-lookup"><span data-stu-id="1d61e-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="1d61e-500">Если выполняется тест **BandwidthPolicyServer**, выходные данные включают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1d61e-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="1d61e-501">Результаты тестирования компьютеров, которые обеспечивают службу политики пропускной способности сервера Lync Server (проверка подлинности) в топологии</span><span class="sxs-lookup"><span data-stu-id="1d61e-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="1d61e-502">Результаты тестирования компьютеров, которые предоставляют службу политики пропускной способности сервера Lync Server (ядро) в топологии.</span><span class="sxs-lookup"><span data-stu-id="1d61e-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-503">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-503">Requirements</span></span>

  - <span data-ttu-id="1d61e-504">Это средство необходимо запускать на компьютере, который входит в топологию и на котором установлено локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="1d61e-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="1d61e-505">Средство должно запускаться администратором, который имеет доступ к локальному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="1d61e-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-506">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-506">Examples</span></span>

<span data-ttu-id="1d61e-507">Ниже приведен пример входных данных средства.</span><span class="sxs-lookup"><span data-stu-id="1d61e-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-508">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-508">Summary</span></span>

<span data-ttu-id="1d61e-509">Это средство может быть полезным ресурсом для администраторов Lync Server 2013, которые хотят проверить состояние серверов, использующих службы политики голосовой связи, видео и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="1d61e-510">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="1d61e-510">Network Configuration Viewer</span></span>

<span data-ttu-id="1d61e-511">Средство просмотра конфигурации сети может использоваться администраторами Microsoft Lync Server 2013 для просмотра топологии сети управления допуском (CAC) для предприятия, обеспечивающего доступ к сеансам связи в реальном времени, таких как голосовые звонки и т. д. видеозвонки с учетом заданной емкости для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="1d61e-512">Lync Server 2013 Administrators определяет политики CAC, принудительно применяемые службами политики пропускной способности, установленными вместе с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-513">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-513">Description</span></span>

<span data-ttu-id="1d61e-514">Средство просмотра конфигурации сети (NetworkConfigurationViewer.exe) позволяет администраторам выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="1d61e-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="1d61e-515">Загружайте и просматривайте топологию сети CAC с помощью Lync Server 2013 для развертывания в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="1d61e-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="1d61e-516">загружать и просматривать сетевую топологию CAC из файла журнала сервера политики пропускной способности в графическом формате;</span><span class="sxs-lookup"><span data-stu-id="1d61e-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="1d61e-517">сохранять сетевую топологию CAC в формате XML на диске;</span><span class="sxs-lookup"><span data-stu-id="1d61e-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="1d61e-518">сохранять схему сетевой топологии CAC в формате JPG или BMP;</span><span class="sxs-lookup"><span data-stu-id="1d61e-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="1d61e-519">просматривать данные конфигурации сетевой топологии CAC;</span><span class="sxs-lookup"><span data-stu-id="1d61e-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="1d61e-520">просматривать сетевую топологию CAC в виде древовидного представления;</span><span class="sxs-lookup"><span data-stu-id="1d61e-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="1d61e-521">определять настраиваемые соединители для каналов сетевой топологии CAC (например каналов между сайтом и областью, между двумя областями или между двумя сайтами);</span><span class="sxs-lookup"><span data-stu-id="1d61e-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="1d61e-522">просматривать сведения о сайтах и областях сетевой топологии CAC, а также о настроенных политиках пропускной способности и сетевых каналах.</span><span class="sxs-lookup"><span data-stu-id="1d61e-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-523">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-523">Purpose</span></span>

<span data-ttu-id="1d61e-524">Просмотр каналов корпоративной сетевой топологии CAC в графическом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="1d61e-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-525">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-525">Examples</span></span>

<span data-ttu-id="1d61e-526">**Загрузите и просмотрите топологию сети CAC с помощью Lync Server 2013 для развертывания в графическом формате:** Lync Server 2013 администраторы могут загружать и просматривать конфигурацию топологии сети CAC на любом компьютере Lync Server 2013 с помощью параметра **конфигурации сети** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="1d61e-527">При развертывании на компьютере, на котором не установлено подключение к хранилищу конфигураций Lync, средству не удастся загрузить или просмотреть такую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1d61e-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="1d61e-528">![Загрузка конфигурации сети.] (images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Загрузка конфигурации сети.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="1d61e-529">**Загрузка и просмотр топологии сети CAC из файла журнала политики пропускной способности в графическом формате:** Серверы политики пропускной способности Lync Server 2013. Сохранение топологии сети CAC в качестве части механизма ведения журнала в местоположении общей папки в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="1d61e-530">Администраторы сервера Lync Server могут просматривать такие файлы в графическом формате с помощью команды " **открыть конфигурацию сети** ", как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="1d61e-531">![Открытие файла журнала политики пропускной способности сервера.] (images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Открытие файла журнала политики пропускной способности сервера.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="1d61e-532">Сохранение топологии сети CAC и сохранение ее в формате XML на диске: Lync Server 2013 администраторы могут сохранить файл конфигурации топологии сети CAC в формате XML с помощью параметра " **сохранить копию конфигурации сети** ", как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="1d61e-533">Сохраненный файл конфигурации можно использовать в автономном режиме для наглядного просмотра.</span><span class="sxs-lookup"><span data-stu-id="1d61e-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="1d61e-534">![Сохранение конфигурации сети в виде XML-файла.] (images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Сохранение конфигурации сети в виде XML-файла.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="1d61e-535">Сохранение и сохранение схемы топологии сети CAC в формате JPG или BMP: Lync Server 2013 администраторы могут сохранять конфигурацию топологии сети CAC в графическом формате (форматы файлов JPG и BMP) с помощью команды " **сохранить схему настройки сети как рисунок** ". параметр, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="1d61e-536">![Сохранение конфигурации сети в виде изображения.] (images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Сохранение конфигурации сети в виде изображения.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="1d61e-537">**Просмотр данных конфигурации топологии сети CAC:** Lync Server 2013 администраторы могут просматривать связанные данные конфигурации сети, такие как регионы сети, сетевые сайты, профили пропускной способности и IP-адреса подсети сайта в текстовом формате с помощью параметра Просмотр данных конфигурации сети, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="1d61e-538">![Просмотр данных конфигурации сети.] (images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Просмотр данных конфигурации сети.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="1d61e-539">**Просмотр топологии сети CAC в стиле представления дерева.** С помощью панели управления в левой части окна инструментов, как показано ниже, администраторы Lync Server 2013 могут просматривать данные сетевой конфигурации в графическом стиле представления дерева.</span><span class="sxs-lookup"><span data-stu-id="1d61e-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="1d61e-540">![Просмотр данных конфигурации сети в представлении в виде дерева.] (images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Просмотр данных конфигурации сети в представлении в виде дерева.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="1d61e-541">**Определите пользовательские соединители для связей топологии сети CAC (например, "сайт-регион", "регион — регион" и "связь между сайтами"):** В Lync Server 2013 администраторы могут определять пользовательские графические соединители для сетевых адаптеров с сетевой конфигурацией CAC с помощью параметра Settings (параметры), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d61e-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="1d61e-542">Это помогает отличать различные типы сетевых ссылок, которые настроены в конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="1d61e-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="1d61e-543">![Определение настраиваемых соединителей для топологии сети CAC] (images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Определение настраиваемых соединителей для топологии сети CAC")</span><span class="sxs-lookup"><span data-stu-id="1d61e-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="1d61e-544">**Просмотр сведений сайта топологии сети CAC, сведений о регионе и стратегий подготовки пропускной способности.** С помощью параметров, показанных ниже, администраторы Lync Server 2013 могут просматривать информацию о сети CAC, информацию о сайте и сведения о подготовке пропускной способности в CAC.</span><span class="sxs-lookup"><span data-stu-id="1d61e-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="1d61e-545">(Например, щелкните элемент **сведения** в сетевом регионе или объекте сетевого сайта.)</span><span class="sxs-lookup"><span data-stu-id="1d61e-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="1d61e-546">![Определение настраиваемых соединителей для сети.] (images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Определение настраиваемых соединителей для сети.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-547">Заключение</span><span class="sxs-lookup"><span data-stu-id="1d61e-547">Summary</span></span>

<span data-ttu-id="1d61e-548">Это средство может быть ценным ресурсом для пользователей Lync Server 2013, которые хотели бы просматривать топологию сети CAC для развертывания в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="1d61e-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="1d61e-549">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="1d61e-549">Response Group Agent Live</span></span>

<span data-ttu-id="1d61e-550">Приложение "группа ответа" дает агентам возможность доступа к полезной информации в реальном времени с помощью встроенной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="1d61e-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="1d61e-551">К сожалению, графическое представление этих данных не доступно за пределами приложения.</span><span class="sxs-lookup"><span data-stu-id="1d61e-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="1d61e-552">Средство "Live Resource Kit" агента группы ответа решает эту проблему, предоставляя простой и графический способ доступа к этим сведениям, дополненный с помощью программного обеспечения Microsoft Lync 2013 для обмена информацией, например наличия других агентов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-553">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-553">Description</span></span>

<span data-ttu-id="1d61e-554">Динамический агент группы ответа — это приложение Windows, которое предоставляет агентам группы ответа функции входа и выхода и некоторые сведения в режиме реального времени (такие как членство в группах и текущее число звонков).</span><span class="sxs-lookup"><span data-stu-id="1d61e-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="1d61e-555">Она должна быть расширенной версией страницы группы агента (доступна в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-556">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-556">Purpose</span></span>

<span data-ttu-id="1d61e-p165">Приложение группы ответа помещает входящие звонки в очередь, а затем направляет их группам агентов. Для принятия обоснованных решений по поводу того, какие звонки следует обслуживать, агенты могут получать доступ к информации о своих группах агентов в режиме реального времени, например к сведениям о том, какие еще агенты доступны и сколько звонков помещено в каждую очередь. Динамический агент группы ответа обеспечивает интуитивно понятный доступ к этой информации, которая ранее была доступна только через службу группы ответа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p165">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="1d61e-560">Возможности</span><span class="sxs-lookup"><span data-stu-id="1d61e-560">Features</span></span>

<span data-ttu-id="1d61e-561">Средство агента групп ответов создано в службе групп ответов и Microsoft Lync 2013 SDK.</span><span class="sxs-lookup"><span data-stu-id="1d61e-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="1d61e-562">Он предоставляет агентам группы ответа информацию и возможности, доступные в службе группе ответа (например сведения о членстве в группах, присутствии других агентов и числе ожидающих звонков).</span><span class="sxs-lookup"><span data-stu-id="1d61e-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="1d61e-563">На рисунке ниже показан главный интерфейс динамического агента группы ответа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="1d61e-564">![Средство агента группы ответа в реальном времени.] (images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Средство агента группы ответа в реальном времени.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="1d61e-565">В динамическом агенте группы ответа доступны следующие три основные функции.</span><span class="sxs-lookup"><span data-stu-id="1d61e-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="1d61e-566">**Вход в службу.** Вопреки странице "группы агента" (доступ к Lync 2013), агент группы ответа Live позволяет только агентам входить и выходить из всех групп агента одновременно.</span><span class="sxs-lookup"><span data-stu-id="1d61e-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="1d61e-567">Это приложение предоставляет агентам три быстрых способа входа или выхода.</span><span class="sxs-lookup"><span data-stu-id="1d61e-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="1d61e-568">Нажмите в приложении кнопку входа или выхода (зеленую или красную соответственно).</span><span class="sxs-lookup"><span data-stu-id="1d61e-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="1d61e-569">Щелкните значок в области уведомлений и выберите команду входа или выхода.</span><span class="sxs-lookup"><span data-stu-id="1d61e-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="1d61e-570">Используйте настраиваемые сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="1d61e-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="1d61e-571">**Участие** в группах: Если выбрана группа агента, агент группы ответов Live отображает список агентов в этой группе на правой панели.</span><span class="sxs-lookup"><span data-stu-id="1d61e-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="1d61e-572">Если Lync 2013 запущен на том же компьютере, что и это приложение, сведения о присутствии и карточка контакта отображаются в агенте группы ответа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="1d61e-573">Агенты могут отправлять мгновенные сообщения или звонить другим агентам непосредственно отсюда.</span><span class="sxs-lookup"><span data-stu-id="1d61e-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="1d61e-p169">**Статистика в режиме реального времени**. Динамический агент группы ответа предоставляет статистику в режиме реального времени по всем группам агентов. Частота обновления составляет одну минуту. Когда группа ответа отвечает на звонок, рядом с именем группы появляется визуальный индикатор с текущим числом звонков в очереди. Если навести указатель на группу, также отображается самое долгое время ожидания.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p169">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-578">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-578">Requirements</span></span>

<span data-ttu-id="1d61e-579">Для динамического агента группы ответа требуется платформа .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="1d61e-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="1d61e-580">Кроме того, чтобы воспользоваться преимуществами функций присутствия и карточки контакта, Lync 2013 должен быть установлен локально (и запущен).</span><span class="sxs-lookup"><span data-stu-id="1d61e-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="1d61e-581">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="1d61e-581">Configuration</span></span>

<span data-ttu-id="1d61e-p171">Динамический агент группы ответа можно настроить в соответствии с личными предпочтениями с помощью диалогового окна Options (Параметры) приложения. Кроме того, администратор может определить адрес узла по умолчанию, изменив свойство defaultHostAddress в файле RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p171">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="1d61e-p172">На приведенном ниже рисунке показано диалоговое окно Options, с помощью которого агенты могут настраивать адрес узла и сочетания клавиш. Чтобы открыть его, нажмите кнопку Options в правом верхнем углу главного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p172">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="1d61e-586">![Диалоговое окно "Параметры" агента группы ответа "живые".] (images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Диалоговое окно \"Параметры\" агента группы ответа \"живые\".")</span><span class="sxs-lookup"><span data-stu-id="1d61e-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="1d61e-587">В конфигурации динамического агента группы ответа можно настроить следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="1d61e-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="1d61e-p173">Host address (Имя узла) — обычно это полное доменное имя веб-пула, входящего в домашний пул агента. Адрес службы группы ответа автоматически формируется на основе этой информации (путем добавления соответствующего пути после имени узла).</span><span class="sxs-lookup"><span data-stu-id="1d61e-p173">Host address: This is typically the web pool FQDN belonging to the agent’s home pool. The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="1d61e-p174">Shortcuts (Сочетания клавиш) — можно настроить сочетания клавиш, используемые для входа и выхода. Единственным условием является то, что оба сочетания клавиш должны включать клавишу с логотипом Windows (и по крайней мере еще одну клавишу).</span><span class="sxs-lookup"><span data-stu-id="1d61e-p174">Shortcuts: The exact shortcuts to sign-in/out can be customized. The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="1d61e-592">Start with Windows (Запускать при загрузке Windows) — приложение можно настроить так, чтобы оно запускалось автоматически при загрузке ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="1d61e-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-593">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-593">Examples</span></span>

<span data-ttu-id="1d61e-594">На приведенном ниже рисунке показано, как позвонить или отправить мгновенное сообщение другому агенту, щелкнув правой кнопкой мыши контакт в области справа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="1d61e-595">![Совершение звонков и отправка мгновенных сообщений.] (images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Совершение звонков и отправка мгновенных сообщений.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="1d61e-596">На приведенном ниже рисунке показано, как в динамическом агенте группы ответа отображается текущее число звонков в очереди и самое долгое время ожидания для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="1d61e-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="1d61e-597">![Просмотр сведений об очереди.] (images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Просмотр сведений об очереди.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-598">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-598">Summary</span></span>

<span data-ttu-id="1d61e-599">Агент группы ответа предоставляет такие полезные функции, как быстрый вход и выход, сведения о членстве в группах и базовая статистика в режиме реального времени, которые вне приложения доступны только посредством службы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="1d61e-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="1d61e-600">С помощью средства Live Resource Kit агента группы ответа администраторы Lync могут предоставлять свои агенты с помощью приложения Windows, позволяющего выполнять задачи быстрее и в графическом виде.</span><span class="sxs-lookup"><span data-stu-id="1d61e-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="1d61e-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="1d61e-601">SEFAUtil</span></span>

<span data-ttu-id="1d61e-602">Сефаутил (вспомогательная Активация компонентов расширения) — это средство командной строки, которое позволяет администраторам и агентам службы поддержки Microsoft Lync Server 2013 создавать и настраивать делегирование звонков, переадресацию звонка, Одновременный звонок, командный Звонок параметры и Отправка группового звонка от имени пользователя Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="1d61e-603">Кроме того, с помощью этого средства администраторы могут запрашивать параметры маршрутизации звонков, опубликованные для определенного пользователя. С помощью средства Сефаутил администратор может включить/отключить/изменить переадресацию звонков или одновременно звонить от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="1d61e-604">Администратор может указать целевой объект (в форме универсального кода ресурса (URI) SIP) или использовать цель, уже опубликованную пользователем.</span><span class="sxs-lookup"><span data-stu-id="1d61e-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="1d61e-605">Это средство также позволяет администраторам добавлять или удалять делегатов или участников группы приема звонков от имени пользователя. Этот инструмент создан на основе управляемого API Microsoft Unified Communications (УКМА) 3,0 и требует, чтобы администраторы создавали надежное приложение в хранилище Центрального управления для Сефаутил</span><span class="sxs-lookup"><span data-stu-id="1d61e-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="1d61e-606">Сефаутил (активация дополнительных компонентов расширения) позволяет администраторам Lync Server 2013 и агентам службы поддержки настраивать делегирование звонков, переадресацию звонков, одновременную звонок, параметры группового звонка и рассылку групповых звонков от имени пользователя Lync Server 2013 .</span><span class="sxs-lookup"><span data-stu-id="1d61e-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="1d61e-607">Оно также позволяет администраторам запрашивать параметры маршрутизации звонков, опубликованные для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-608">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-608">Description</span></span>

<span data-ttu-id="1d61e-609">Текущая версия Сефаутил — это только инструмент командной строки; не существует поддерживающего графический интерфейс пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="1d61e-610">Это средство основано на управляемом интерфейсе API Microsoft Unified Communications (УКМА) 3,0.</span><span class="sxs-lookup"><span data-stu-id="1d61e-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="1d61e-611">Возможности, доступные в этом средстве, позволяют администраторам и агентам службы поддержки выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1d61e-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="1d61e-612">просматривать все параметры маршрутизации звонков для пользователя (включая параметры переадресации звонков, делегирования, одновременных звонков, групповых звонков и группового ответа на звонки);</span><span class="sxs-lookup"><span data-stu-id="1d61e-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="1d61e-613">включать, отключать и изменять параметры переадресации звонков (включая назначение и таймер ожидания ответа);</span><span class="sxs-lookup"><span data-stu-id="1d61e-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="1d61e-614">включать, отключать и изменять непосредственные конфигурации переадресации звонков;</span><span class="sxs-lookup"><span data-stu-id="1d61e-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="1d61e-615">включать, отключать и изменять параметры делегирования;</span><span class="sxs-lookup"><span data-stu-id="1d61e-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="1d61e-616">включать, отключать и изменять параметры группы приема звонков;</span><span class="sxs-lookup"><span data-stu-id="1d61e-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d61e-617">Новая программа Lync Server 2013 Сефаутил</span><span class="sxs-lookup"><span data-stu-id="1d61e-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="1d61e-618">включать, отключать и изменять параметры одновременных звонков (включая назначение);</span><span class="sxs-lookup"><span data-stu-id="1d61e-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d61e-619">Новая программа Lync Server 2013 Сефаутил</span><span class="sxs-lookup"><span data-stu-id="1d61e-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="1d61e-620">включать, отключать и изменять параметры группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1d61e-621">Новая программа Lync Server 2013 Сефаутил</span><span class="sxs-lookup"><span data-stu-id="1d61e-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="1d61e-622">В отношении средства действуют перечисленные ниже ограничения.</span><span class="sxs-lookup"><span data-stu-id="1d61e-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="1d61e-623">Поддерживается только для пользователей, размещенных в пуле сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="1d61e-624">Групповое изменение параметров маршрутизации звонков для нескольких пользователей не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1d61e-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-625">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-625">Output</span></span>

<span data-ttu-id="1d61e-p179">В текущей версии средства данные выводятся только в окне командной строки. Подробные сведения см. в разделе «Примеры» далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p179">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-628">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-628">Purpose</span></span>

<span data-ttu-id="1d61e-629">Ниже приведены некоторые основные сценарии, в которых можно использовать это средство.</span><span class="sxs-lookup"><span data-stu-id="1d61e-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="1d61e-630">Боб является руководителем и перенесен в телефонную связь Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d61e-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="1d61e-631">У него есть делегирование для существующей системы УАТС.</span><span class="sxs-lookup"><span data-stu-id="1d61e-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="1d61e-632">В процессе перемещения в Lync администратор может настроить маршрутизацию Боба, чтобы она отражала свое уже существовавшее конфигурирование делегирования.</span><span class="sxs-lookup"><span data-stu-id="1d61e-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="1d61e-p181">Юлия находится в командировке и должна получить важный звонок от одного из клиентов. Однако она находится в гостинице и не имеет доступа к компьютеру. Юлия звонит в службу технической поддержки и просит, чтобы все звонки на ее рабочий номер переадресовывались на номер мобильного телефона. Специалисты службы поддержки производят настройку от ее имени.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p181">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="1d61e-p182">Звонки на рабочий номер Алексея поступают в его мобильную голосовую почту, когда он находится на работе. Однако в других местах все работает правильно. Специалист службы технической поддержки просматривает настройки маршрутизации Алексея и обнаруживает, что у него настроены одновременные звонки на мобильный телефон. Специалист интересуется у Алексея, насколько стабильна мобильная связь в его офисе, и устанавливает, что звонки поступают в мобильную голосовую почту из-за правила одновременных звонков, если сигнал мобильной сети слабый.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p182">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations. The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone. The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="1d61e-640">Майк является новым сотрудником компании Contoso и присоединяется к новой команде, для которой настроены все пользователи, при включении в Microsoft Lync администратор может настроить параметры своей группы приема звонков, чтобы включить все свои члены группы, а также администратор добавляет пользователя Mike в группу приема звонков для каждого участника в своей группе.</span><span class="sxs-lookup"><span data-stu-id="1d61e-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="1d61e-641">В отделе кадров компании Contoso все абоненты обслуживаются специалистами с первого звонка.</span><span class="sxs-lookup"><span data-stu-id="1d61e-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="1d61e-642">При групповых звонках все телефоны звонят одновременно, что отвлекает сотрудников отдела от работы.</span><span class="sxs-lookup"><span data-stu-id="1d61e-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="1d61e-643">Чтобы обеспечить наилучшее обслуживание, не нарушая участников группы, администратор Lync использует преимущества функции отправки группового звонка.</span><span class="sxs-lookup"><span data-stu-id="1d61e-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="1d61e-644">Он добавляет всех сотрудников отдела в группу ответа и сообщает им номер этой группы.</span><span class="sxs-lookup"><span data-stu-id="1d61e-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="1d61e-645">Когда Светланы нет на рабочем месте, Алексей, замечая, что ее телефон звонит, может ответить на звонок со своего рабочего места.</span><span class="sxs-lookup"><span data-stu-id="1d61e-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-646">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-646">Requirements</span></span>

<span data-ttu-id="1d61e-p184">Средство SEFAUtil можно запускать только на компьютере, входящем в пул доверенных приложений. На этом компьютере должен быть установлен интерфейс UCMA 3.0. Для запуска средства в пуле необходимо создать доверенное приложение с идентификатором приложения SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p184">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="1d61e-650">**Создание доверенного приложения для средства SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="1d61e-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="1d61e-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span><span class="sxs-lookup"><span data-stu-id="1d61e-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="1d61e-652">При необходимости вы можете добавить пул в качестве нового надежного пула приложений с помощью командной консоли Lync Server с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="1d61e-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d61e-653">Интерфейс UCMA 3.0 нужно установить на всех компьютерах, на которых будет запускаться средство SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="1d61e-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="1d61e-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span><span class="sxs-lookup"><span data-stu-id="1d61e-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="1d61e-655">Чтобы определить Сефаутил как новое надежное приложение, используйте командную консоль Lync Server Management Shell и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1d61e-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d61e-656">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="1d61e-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="1d61e-657">The topology changes need to be enabled.</span><span class="sxs-lookup"><span data-stu-id="1d61e-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="1d61e-658">Включить изменения топологии можно с помощью командной консоли Lync Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="1d61e-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="1d61e-659">При необходимости установите средства набора ресурсов для Lync Server 2013 на сервер, который будет использоваться для запуска средства Сефаутил (сервер должен входить в состав надежного пула приложений).</span><span class="sxs-lookup"><span data-stu-id="1d61e-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="1d61e-660">Убедитесь в том, что средство SEFAUtil работает правильно.</span><span class="sxs-lookup"><span data-stu-id="1d61e-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="1d61e-661">Для этого запустите его из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="1d61e-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="1d61e-662">По умолчанию средство будет находиться в: "...". \\Файлы\\программ Microsoft Lync Server 2013\\рескит ".</span><span class="sxs-lookup"><span data-stu-id="1d61e-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="1d61e-663">Чтобы вывести на экран параметры переадресации звонков пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d61e-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="1d61e-664">На экране должны появиться параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="1d61e-665">Групповой ответ на звонки</span><span class="sxs-lookup"><span data-stu-id="1d61e-665">Group Call Pickup</span></span>

<span data-ttu-id="1d61e-666">Для отправки группового звонка требуется дополнительная настройка в Lync Server, чтобы обеспечить возможность полного включения возможности.</span><span class="sxs-lookup"><span data-stu-id="1d61e-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="1d61e-667">Перед тем как назначать группы ответа пользователям, обратитесь к документации по функции группового ответа на звонки, чтобы получить инструкции по ее планированию и развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1d61e-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-668">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="1d61e-669">Отображение текущих параметров обработки звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="1d61e-670">Следующая команда выводит параметры обработки звонков для пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-671">В этом примере ключ <STRONG>/Server</STRONG> используется для указания сервера Lync Server, к которому нужно подключиться.</span><span class="sxs-lookup"><span data-stu-id="1d61e-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="1d61e-672">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="1d61e-673">Задание назначения для переадресации звонков и неотвеченных звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="1d61e-674">В этом примере задается направление переадресации, назначение ответа и Задержка звонка.</span><span class="sxs-lookup"><span data-stu-id="1d61e-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="1d61e-675">Параметр/Server не предоставляется; Сефаутил пытается выполнить Автообнаружение сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="1d61e-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="1d61e-676">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="1d61e-677">Немедленное включение переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="1d61e-678">В этом примере немедленно включается переадресация звонков другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="1d61e-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="1d61e-679">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="1d61e-680">Немедленное отключение переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="1d61e-681">В этом примере немедленно отключается переадресация звонков.</span><span class="sxs-lookup"><span data-stu-id="1d61e-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="1d61e-682">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="1d61e-683">Добавление пользователя в качестве делегата и настройка одновременных звонков делегатам</span><span class="sxs-lookup"><span data-stu-id="1d61e-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="1d61e-684">В этом примере пользователь добавляется в качестве делегата и настраиваются одновременные звонки делегатам.</span><span class="sxs-lookup"><span data-stu-id="1d61e-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="1d61e-685">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="1d61e-686">Изменение правила одновременных звонков делегатам</span><span class="sxs-lookup"><span data-stu-id="1d61e-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="1d61e-687">В этом примере правило одновременных звонков, настроенное в предыдущем примере, изменяется на правило задержки звонков.</span><span class="sxs-lookup"><span data-stu-id="1d61e-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="1d61e-688">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="1d61e-689">Удаление делегата</span><span class="sxs-lookup"><span data-stu-id="1d61e-689">Remove the Delegate</span></span>

<span data-ttu-id="1d61e-690">В этом примере удаляется делегат.</span><span class="sxs-lookup"><span data-stu-id="1d61e-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-691">После удаления последнего делегата делегированные звонки автоматически отключаются.</span><span class="sxs-lookup"><span data-stu-id="1d61e-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="1d61e-692">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="1d61e-693">Добавление делегата и настройка правила переадресации звонков делегатам</span><span class="sxs-lookup"><span data-stu-id="1d61e-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="1d61e-694">В этом примере добавляется делегат и настраивается правило переадресации звонков делегатам.</span><span class="sxs-lookup"><span data-stu-id="1d61e-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="1d61e-695">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="1d61e-696">Включение одновременных звонков и задание номера назначения</span><span class="sxs-lookup"><span data-stu-id="1d61e-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="1d61e-697">В этом примере включаются одновременные звонки и задается номер назначения для них.</span><span class="sxs-lookup"><span data-stu-id="1d61e-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-698">Чтобы изменить номер назначения одновременных звонков для пользователя, для которого уже включены одновременные звонки, используйте в команде параметр /enablesimulring. В противном случае номер назначения не изменится.</span><span class="sxs-lookup"><span data-stu-id="1d61e-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="1d61e-699">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="1d61e-700">Отключение одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="1d61e-701">В этом примере отключаются одновременные звонки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="1d61e-702">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="1d61e-703">Добавление пользователя в группу приема звонков и настройка одновременных звонков группе приема звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="1d61e-704">В этом примере добавляется член группы приема звонков и включаются одновременные звонки этой группе.</span><span class="sxs-lookup"><span data-stu-id="1d61e-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-705">При добавлении члена в группу приема звонков пользователя параметры одновременных звонков автоматически изменяются на выполнение одновременных звонков в эту группу.</span><span class="sxs-lookup"><span data-stu-id="1d61e-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="1d61e-706">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="1d61e-707">Удаление члена из группы приема звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="1d61e-708">В этом примере удаляется один из членов группы приема звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-709">Если удаляемый член является единственным в группе приема звонков, одновременные звонки группе приема звонков автоматически отключаются.</span><span class="sxs-lookup"><span data-stu-id="1d61e-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="1d61e-710">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="1d61e-711">Настройка задержки звонков в группу приема звонков</span><span class="sxs-lookup"><span data-stu-id="1d61e-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="1d61e-712">В этом примере изменяется параметр задержки звонков в группу приема звонков.</span><span class="sxs-lookup"><span data-stu-id="1d61e-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="1d61e-713">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="1d61e-714">Включение группового звонка</span><span class="sxs-lookup"><span data-stu-id="1d61e-714">Enable Team-Call</span></span>

<span data-ttu-id="1d61e-715">В этом примере включается групповой звонок для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-716">Если группа ответа звонков пользователя не имеет членов, групповой звонок не будет включен.</span><span class="sxs-lookup"><span data-stu-id="1d61e-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="1d61e-717">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="1d61e-718">Отключение группового звонка</span><span class="sxs-lookup"><span data-stu-id="1d61e-718">Disable Team-Call</span></span>

<span data-ttu-id="1d61e-719">В этом примере отключается групповой звонок для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="1d61e-720">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="1d61e-721">Включение группового ответа на звонки и назначение группы ответа пользователю</span><span class="sxs-lookup"><span data-stu-id="1d61e-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="1d61e-722">В этом примере пользователю назначается группа ответа и включается групповой ответ на звонки.</span><span class="sxs-lookup"><span data-stu-id="1d61e-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="1d61e-723">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="1d61e-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="1d61e-724">Отключение группового ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="1d61e-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="1d61e-725">В этом примере отключается групповой ответ на звонки для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-p191">Когда вы отключаете функцию группового ответа на звонки для пользователя, номер группы, который был назначен пользователю, не сохраняется. Если вы впоследствии повторно включаете функцию группового ответа на звонки для данного пользователя, необходимо снова назначить номер группы с помощью параметра /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p191">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="1d61e-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="1d61e-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-729">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-729">Description</span></span>

<span data-ttu-id="1d61e-730">SYSPrep. ps1 — это сценарий Windows PowerShell, который будет устанавливать следующие предварительные требования Lync Server 2013 на компьютере с операционной системой Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1d61e-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="1d61e-731">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1d61e-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="1d61e-732">Microsoft SQL Server, экспресс-выпуск</span><span class="sxs-lookup"><span data-stu-id="1d61e-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="1d61e-733">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="1d61e-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="1d61e-734">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="1d61e-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="1d61e-735">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="1d61e-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="1d61e-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="1d61e-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="1d61e-737">Основные файлы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61e-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="1d61e-738">Хотя имя этого сценария совпадает с именем средства SysPrep для операционных систем Microsoft Windows, эти средства отличаются.</span><span class="sxs-lookup"><span data-stu-id="1d61e-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="1d61e-739">Этот сценарий установит необходимые компоненты для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="1d61e-740">После установки этих компонентов можно создать образ сервера с помощью средства SysPrep Windows.</span><span class="sxs-lookup"><span data-stu-id="1d61e-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-741">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-741">Requirements</span></span>

<span data-ttu-id="1d61e-742">Перед запуском сценария SYSPrep. ps1 необходимо скопировать необходимые файлы в локальную папку на компьютере с операционной системой Windows Server 2008 (например, **D:\\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="1d61e-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="1d61e-743">В этой папке также должна быть копия файлов Lync Server 2013, а именно файл **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="1d61e-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="1d61e-744">Файлы необходимых компонентов можно загрузить на следующих страницах.</span><span class="sxs-lookup"><span data-stu-id="1d61e-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d61e-745">Необходимый компонент</span><span class="sxs-lookup"><span data-stu-id="1d61e-745">Prerequisite</span></span></th>
<th><span data-ttu-id="1d61e-746">Расположение</span><span class="sxs-lookup"><span data-stu-id="1d61e-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d61e-747">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1d61e-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d61e-748">Microsoft SQL Server 2008 R2, экспресс-выпуск</span><span class="sxs-lookup"><span data-stu-id="1d61e-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d61e-749">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="1d61e-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d61e-750">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="1d61e-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d61e-751">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="1d61e-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d61e-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="1d61e-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d61e-753">Lync Server 2013 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="1d61e-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="1d61e-754">Копирование из Lync Server 2013 Media</span><span class="sxs-lookup"><span data-stu-id="1d61e-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="1d61e-755">Параметр</span><span class="sxs-lookup"><span data-stu-id="1d61e-755">Parameter</span></span>

<span data-ttu-id="1d61e-756">Параметр **–SetupFolder** использует в качестве аргумента расположение каталога с файлами необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="1d61e-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-757">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-757">Examples</span></span>

<span data-ttu-id="1d61e-758">Чтобы запустить сценарий SYSPrep. ps1 и установить необходимые компоненты Lync Server 2013, выполните следующую команду из командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="1d61e-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="1d61e-759">Перенос оповещений о неназначенных номерах</span><span class="sxs-lookup"><span data-stu-id="1d61e-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="1d61e-760">Это средство миграции "неназначенные номера" позволяет администратору Lync переместить неназначенные номера, настроенные приложением-объявлением из исходного сервера или пула Lync, на целевой сервер или в организатор.</span><span class="sxs-lookup"><span data-stu-id="1d61e-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-761">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-761">Description</span></span>

<span data-ttu-id="1d61e-762">Средство переноса оповещений о неназначенных номерах — это сценарий Windows PowerShell, который перемещает конфигурацию неназначенных номеров, обслуживаемую приложением «Оповещение», с исходного сервера (или пула) на другой.</span><span class="sxs-lookup"><span data-stu-id="1d61e-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="1d61e-763">При запуске сценарий переноса оповещений о неназначенных номерах выполняет следующие операции.</span><span class="sxs-lookup"><span data-stu-id="1d61e-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="1d61e-764">Переносит все звуковые файлы, которые используются оповещениями о неназначенных номерах в приложении «Оповещение», размещенном на исходном сервере или в исходном пуле, в хранилище файлов конечного сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="1d61e-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d61e-765">звуковые файлы удаляются из исходного пула после того, как они будут скопированы в конечный пул.</span><span class="sxs-lookup"><span data-stu-id="1d61e-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="1d61e-766">Переносит все оповещения о неназначенных номерах, которые настроены для приложения «Оповещение», размещенного на исходном сервере или в исходном пуле, на конечный сервер или в конечный пул.</span><span class="sxs-lookup"><span data-stu-id="1d61e-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="1d61e-767">Переназначает все диапазоны неназначенных номеров, которые обслуживаются приложением «Оповещение», размещенным на исходном сервере или в исходном пуле, конечному серверу или пулу.</span><span class="sxs-lookup"><span data-stu-id="1d61e-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="1d61e-768">После успешного выполнения сценария все диапазоны неназначенных номеров, которые обслуживались приложением «Оповещение», размещенным на исходном сервере или в исходном пуле, будут обслуживаться конечным сервером или пулом с сохранением конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d61e-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-769">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-769">Output</span></span>

<span data-ttu-id="1d61e-770">Сценарий **Move-ксаннаунцементконфигуратион** указывает, что в окне командной консоли Lync вы выполнили успешное или сбой операции миграции.</span><span class="sxs-lookup"><span data-stu-id="1d61e-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="1d61e-p194">Если выполнение операции было прервано в результате ошибки, успешно перенесенные диапазоны неназначенных номеров останутся на конечном сервере или в конечном пуле и будут работоспособны, а остальные диапазоны останутся на исходном сервере или в исходном пуле и также будут работоспособны. Чтобы полностью перенести конфигурацию, устраните причину ошибки и повторно запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p194">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="1d61e-773">Назначение</span><span class="sxs-lookup"><span data-stu-id="1d61e-773">Purpose</span></span>

<span data-ttu-id="1d61e-774">Сценарий переноса оповещений о неназначенных номерах можно использовать в следующих трех сценариях.</span><span class="sxs-lookup"><span data-stu-id="1d61e-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="1d61e-775">**Перенос параметров конфигурации в новую версию Lync Server.** Компания Contoso находится в процессе перехода на Lync Server 2013 и в процессе миграции администратор сервера Lync Server хотел бы переместить неназначенные номера, настроенные приложением из развертывания Lync Server 2010 на новое развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="1d61e-776">Для перемещения параметров конфигурации администратор сервера Lync использует средство миграции "неназначенные номера объявлений".</span><span class="sxs-lookup"><span data-stu-id="1d61e-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="1d61e-777">**Откат развертывания с Lync server 2013 на Lync server 2010:** Из-за непредвиденных факторов компания Contoso должна откатить миграцию на новое развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="1d61e-778">Чтобы свести к минимуму перерывы для службы, администратор сервера Lync Server использует неназначенный номер, чтобы откатить конфигурацию из развертывания Lync Server 2013 в развертывание Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1d61e-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="1d61e-779">**Перемещение данных между развертыванием Lync.** Компания Contoso — это процесс замены всех серверов одного пула на новые.</span><span class="sxs-lookup"><span data-stu-id="1d61e-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="1d61e-780">Их стратегия состоит в том, чтобы развернуть новый пул Lync Server 2013, переместить все данные из старого в новый пул, а затем использовать старый пул.</span><span class="sxs-lookup"><span data-stu-id="1d61e-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="1d61e-781">После развертывания нового пула конфигурация переносится из старого пула в новый с помощью средства переноса оповещений о неназначенных номерах.</span><span class="sxs-lookup"><span data-stu-id="1d61e-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-782">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-782">Requirements</span></span>

<span data-ttu-id="1d61e-783">Для успешной работы средства должны выполняться перечисленные ниже основные требования.</span><span class="sxs-lookup"><span data-stu-id="1d61e-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="1d61e-784">Сценарий необходимо запускать с компьютера, на котором установлена консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d61e-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="1d61e-785">Приложение объявлений должно быть успешно развернуто на исходном и целевом серверах или пулах Lync.</span><span class="sxs-lookup"><span data-stu-id="1d61e-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="1d61e-786">Сценарий Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="1d61e-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="1d61e-787">Сценарий Move-CsAnnouncementConfiguration требует использования двух параметров, которые описаны в таблице ниже. </span><span class="sxs-lookup"><span data-stu-id="1d61e-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="1d61e-788">![Параметры перемещения и ксаннаунцементконфигуратион.] (images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Параметры перемещения и ксаннаунцементконфигуратион.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-789">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="1d61e-790">Перемещение неназначенного числа объявлений из пула Lync Server 2010 в пул Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d61e-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="1d61e-791">В этом примере из исходного пула (Lync Server 2010) перемещается число извещений о неназначенном номере из источника в пул назначения (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="1d61e-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="1d61e-792">Перемещение неназначенного числа объявлений из пула Lync Server 2013 в пул Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1d61e-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="1d61e-793">В этом примере из исходного пула (Lync Server 2013) перемещается число извещений о неназначенном номере из источника в пул назначения (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="1d61e-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="1d61e-794">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="1d61e-794">Web Conf Data</span></span>

<span data-ttu-id="1d61e-795">Средство Web CONF Data Tools позволяет администратору коммуникационного программного обеспечения Lync Server 2013 получить больший контроль над данными, связанными с веб-конференции организатора.</span><span class="sxs-lookup"><span data-stu-id="1d61e-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="1d61e-796">К ним относится возможность удаления данных, связанных с собраниями определенного пользователя, на основе критерия метки времени.</span><span class="sxs-lookup"><span data-stu-id="1d61e-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1d61e-797">Описание</span><span class="sxs-lookup"><span data-stu-id="1d61e-797">Description</span></span>

<span data-ttu-id="1d61e-798">Это средство позволяет администратору выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="1d61e-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="1d61e-799">находить все данные веб-конференций, связанные с отдельным пользователем;</span><span class="sxs-lookup"><span data-stu-id="1d61e-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="1d61e-800">удалять все данные веб-конференций, связанные с отдельным пользователем;</span><span class="sxs-lookup"><span data-stu-id="1d61e-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="1d61e-801">удалять все данные веб-конференций, связанные с отдельным пользователем, старше определенной даты;</span><span class="sxs-lookup"><span data-stu-id="1d61e-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="1d61e-802">переносить все данные веб-конференций, связанные с отдельным пользователем, если этот пользователь переносится из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="1d61e-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d61e-803">Средства набора ресурсов для Lync Server 2010 поддерживают перенос всех данных веб-конференций, связанных с одним пользователем, когда пользователь перемещается из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="1d61e-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="1d61e-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span><span class="sxs-lookup"><span data-stu-id="1d61e-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="1d61e-805">Подробнее об этом параметре можно узнать в командлете <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="1d61e-805">For details about this parameter, see the <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="1d61e-p200">Средство удаляет данные только для неактивных собраний. Активные собрания (или собрания в рамках сеансов) удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p200">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="1d61e-p201">Это средство необходимо запускать на компьютере, который входит в тот же пул, что и целевой пользователь. Пользователь, для управления данными собраний которого используется это средство, должен быть размещен в том же пуле пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p201">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1d61e-810">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d61e-810">Output</span></span>

<span data-ttu-id="1d61e-811">Средство выводит результаты каждой операции.</span><span class="sxs-lookup"><span data-stu-id="1d61e-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="1d61e-812">Если выполняется запрос, средство выводит список всех папок с данными неактивных собраний, организатором которых является указанный пользователь.</span><span class="sxs-lookup"><span data-stu-id="1d61e-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="1d61e-813">Если выполняется удаление, средство выводит список всех папок с данными собраний, которые будут удалены.</span><span class="sxs-lookup"><span data-stu-id="1d61e-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1d61e-814">Требования</span><span class="sxs-lookup"><span data-stu-id="1d61e-814">Requirements</span></span>

<span data-ttu-id="1d61e-815">Средство необходимо запускать в том же пуле, в котором в настоящее время размещен организатор.</span><span class="sxs-lookup"><span data-stu-id="1d61e-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="1d61e-816">Средство должно запускаться с правами администратора на доступ к хранилищу файлов содержимого.</span><span class="sxs-lookup"><span data-stu-id="1d61e-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="1d61e-817">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d61e-817">Examples</span></span>

<span data-ttu-id="1d61e-818">В приведенной ниже таблице описываются параметры, некоторые из которых используются в примерах.</span><span class="sxs-lookup"><span data-stu-id="1d61e-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="1d61e-819">![Параметры средства для данных Web CONF.] (images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Параметры средства для данных Web CONF.")</span><span class="sxs-lookup"><span data-stu-id="1d61e-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="1d61e-p202">В предыдущем примере показано, как выполняется команда запроса. Выходные данные этой команды представляют собой список всех папок с содержимым собраний, которые будут затронуты при работе средства.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p202">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="1d61e-p203">Выше приведен пример команды удаления. Она удаляет все папки неактивных собраний для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d61e-p203">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="1d61e-824">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d61e-824">Summary</span></span>

<span data-ttu-id="1d61e-825">Это средство может быть ценным ресурсом для администраторов, которым требуется более полный контроль над данными конференций.</span><span class="sxs-lookup"><span data-stu-id="1d61e-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
