---
title: Документация по средствам набора ресурсов Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c2260f5729c45455596f0ab2477f7a190ef520
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509226"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="94feb-102">Документация по средствам набора ресурсов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94feb-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94feb-103">_**Последнее изменение темы:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="94feb-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="94feb-104">В этом разделе описываются средства, которые входят в состав набора ресурсов Lync Server 2013, в том числе назначение каждого средства, а также примеры их использования. Lync Server 2013, средства набора ресурсов помогают упростить выполнение повседневных задач для ИТ администраторов, которые развертывают Lync Server 2013 и управляют им.</span><span class="sxs-lookup"><span data-stu-id="94feb-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="94feb-105">Например, с помощью средства **Web CONF Data** можно легко управлять данными, отправляемыми пользователями во время собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="94feb-106">Средство **SEFAUtil** можно использовать для настройки переадресации вызовов делегатов и ответа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="94feb-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="94feb-107">Администраторам ИТ рекомендуется использовать эти средства для более эффективного управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="94feb-108">Установка средств набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="94feb-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="94feb-109">Для установки средств набора ресурсов Lync Server 2013, скачайте **OCSReskit.msi**.</span><span class="sxs-lookup"><span data-stu-id="94feb-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="94feb-110">Установщик средств набора ресурсов можно скачать в центре загрузки по адресу [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) .</span><span class="sxs-lookup"><span data-stu-id="94feb-110">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="94feb-111">Запустите **OCSResKit.msi** , чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="94feb-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="94feb-112">MSI устанавливает все средства, указанные в следующем пути: **% Program Files% \\ Microsoft Lync Server 2013 \\ ResKit**.</span><span class="sxs-lookup"><span data-stu-id="94feb-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="94feb-113">В этой папке есть инструменты, которые представляют собой автономные исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="94feb-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="94feb-114">Средства, у которых также есть файлы, находятся в своих вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="94feb-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="94feb-115">Поддерживаемые среды</span><span class="sxs-lookup"><span data-stu-id="94feb-115">Supported Environments</span></span>

<span data-ttu-id="94feb-116">Для оптимальной производительности Lync Server 2013, средства набора ресурсов необходимо установить в той же среде и с теми же спецификациями, что и для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="94feb-117">Общие сведения о средствах набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="94feb-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="94feb-118">В следующем списке описываются средства, доступные в наборе ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="94feb-119">Описание каждого средства, включая требования и пример использования, рассматривается в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="94feb-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="94feb-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="94feb-120">ABSConfig</span></span>

  - <span data-ttu-id="94feb-121">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="94feb-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="94feb-122">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="94feb-123">Вызов Parkometer</span><span class="sxs-lookup"><span data-stu-id="94feb-123">Call Parkometer</span></span>

  - <span data-ttu-id="94feb-124">клеанупсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="94feb-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="94feb-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="94feb-125">DBAnalyze</span></span>

  - <span data-ttu-id="94feb-126">импортсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="94feb-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="94feb-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="94feb-127">LCSSync</span></span>

  - <span data-ttu-id="94feb-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="94feb-128">LookupUserConsole</span></span>

  - <span data-ttu-id="94feb-129">мстурнпинг</span><span class="sxs-lookup"><span data-stu-id="94feb-129">MsTurnPing</span></span>

  - <span data-ttu-id="94feb-130">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="94feb-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="94feb-131">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="94feb-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="94feb-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="94feb-132">SEFAUtil</span></span>

  - <span data-ttu-id="94feb-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="94feb-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="94feb-134">Миграция объявлений неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="94feb-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="94feb-135">Данные Web CONF</span><span class="sxs-lookup"><span data-stu-id="94feb-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="94feb-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="94feb-136">ABSConfig</span></span>

<span data-ttu-id="94feb-137">Средство настройки службы адресной книги (ABSConfig) — это средство администрирования, помогающее администраторам настраивать конфигурацию службы адресной книги в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="94feb-138">Это средство также позволяет администраторам Lync Server 2013 восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94feb-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-139">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-139">Description</span></span>

<span data-ttu-id="94feb-140">ABSConfig — это приложение графического пользовательского интерфейса, которое позволяет администраторам настраивать атрибуты доменных служб Active Directory, связанные со службой адресной книги.</span><span class="sxs-lookup"><span data-stu-id="94feb-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="94feb-141">Ниже приведены основные сценарии для этого средства.</span><span class="sxs-lookup"><span data-stu-id="94feb-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="94feb-142">Чтобы разрешить администраторам сопоставлять атрибуты в доменных службах Active Directory с атрибутами для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="94feb-143">Чтобы разрешить администраторам указывать атрибут доменных служб Active Directory, который необходимо включить или исключить в файлах службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="94feb-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="94feb-144">, Чтобы разрешить администраторам восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94feb-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="94feb-145">Средство ABSConfig можно запустить с помощью файла absConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="94feb-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="94feb-146">Средство откроется на вкладке **Настройка атрибутов** . В этой таблице представлены параметры для сопоставления атрибутов доменных служб Active Directory с полями атрибутов для Lync Server 2013, а также указать пользователей, включаемых или исключаемых из файлов службы адресной книги на основе определенных фильтров атрибутов.</span><span class="sxs-lookup"><span data-stu-id="94feb-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="94feb-147">Кроме того, можно настроить значение номера телефона, включаемого в файл адресной книги.</span><span class="sxs-lookup"><span data-stu-id="94feb-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="94feb-148">Параметр **восстановить значения по умолчанию** позволяет администраторам восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94feb-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="94feb-149">Изменения из Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="94feb-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="94feb-150">В средстве настройки ABS для Lync Server 2013 атрибуты (строки) могут быть удалены путем снятия флажка "включить" для атрибута.</span><span class="sxs-lookup"><span data-stu-id="94feb-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="94feb-151">Это аналогично удалению строки в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="94feb-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-152">Флажок Enable находится в крайнем правом столбце; чтобы просмотреть столбец, возможно, потребуется прокрутить его вправо.</span><span class="sxs-lookup"><span data-stu-id="94feb-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-153">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-153">Output</span></span>

<span data-ttu-id="94feb-154">ABSConfig сохраняет конфигурацию службы адресной книги в базе данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-155">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-155">Purpose</span></span>

<span data-ttu-id="94feb-156">ABSConfig предоставляет быстрый и простой способ настройки службы адресной книги Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-157">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="94feb-158">Компьютер</span><span class="sxs-lookup"><span data-stu-id="94feb-158">Computer</span></span>

<span data-ttu-id="94feb-159">ABSConfig можно запускать только с компьютера, присоединенного к домену, на котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="94feb-160">В случае Lync Server 2013, Enterprise Edition это средство можно запустить на всех серверах переднего плана, на которых в процессе установки включена служба адресной книги.</span><span class="sxs-lookup"><span data-stu-id="94feb-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="94feb-161">Сеть</span><span class="sxs-lookup"><span data-stu-id="94feb-161">Network</span></span>

<span data-ttu-id="94feb-162">Компьютер должен иметь возможность подключения к интерфейсному пулу и серверной базе данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="94feb-163">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="94feb-163">Software</span></span>

<span data-ttu-id="94feb-164">Перед запуском средства ABSConfig необходимо установить следующие компоненты программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="94feb-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="94feb-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94feb-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="94feb-166">Пользователи</span><span class="sxs-lookup"><span data-stu-id="94feb-166">Users</span></span>

<span data-ttu-id="94feb-167">Администраторы, у которых есть разрешения, необходимые для обновления развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-168">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-168">Examples</span></span>

<span data-ttu-id="94feb-169">ABSConfig можно запустить, введя **ABSConfig.exe** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="94feb-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="94feb-170">Ниже показан пользовательский интерфейс средства ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="94feb-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="94feb-171">![Средство ABSConfig.exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Средство ABSConfig.exe.")</span><span class="sxs-lookup"><span data-stu-id="94feb-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-172">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-172">Summary</span></span>

<span data-ttu-id="94feb-173">Средство ABSConfig предоставляет администраторам быстрые и простые в использовании средства для настройки службы адресной книги Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="94feb-174">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="94feb-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="94feb-175">Средство мониторинга службы политики пропускной способности позволяет администраторам просматривать список следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="94feb-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="94feb-176">Все настроенные службы политики пропускной способности Lync Server 2013 (проверка подлинности и ядро) в топологии</span><span class="sxs-lookup"><span data-stu-id="94feb-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="94feb-177">Подключения, которые каждая служба делает с другими службами политики пропускной способности и с пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="94feb-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="94feb-178">Все ссылки, настроенные в документе конфигурации сети и использование пропускной способности в режиме реального времени, отображаются каждой из служб политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="94feb-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-179">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-179">Description</span></span>

<span data-ttu-id="94feb-180">Монитор службы политики пропускной способности реализован в виде приложения, основанного на пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="94feb-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="94feb-181">Администраторы запускают средство, запуская PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="94feb-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="94feb-182">При запуске средства будет предпринята попытка обнаружить список служб политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="94feb-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="94feb-183">После первоначального обновления область слева от окна заполняется списком служб, сгруппированных по кластерам, к которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="94feb-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="94feb-184">Когда Администраторы выбирают определенную службу политики пропускной способности, в области справа отображаются сведения о конкретной службе.</span><span class="sxs-lookup"><span data-stu-id="94feb-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="94feb-185">Эта область также содержит две основные вкладки, отображающие информацию.</span><span class="sxs-lookup"><span data-stu-id="94feb-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="94feb-186">Вкладка "сведения о компьютере"</span><span class="sxs-lookup"><span data-stu-id="94feb-186">Machine Info Tab</span></span>

<span data-ttu-id="94feb-187">На вкладке **сведения о компьютере** отображаются сведения о выбранном службе политики пропускной способности, а также список и состояние всех подключений, выполняемых выбранной службой политики пропускной способности, к другим службам.</span><span class="sxs-lookup"><span data-stu-id="94feb-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="94feb-188">Вкладка "сведения о топологии"</span><span class="sxs-lookup"><span data-stu-id="94feb-188">Topology Info Tab</span></span>

<span data-ttu-id="94feb-189">На вкладке **сведения о топологии** отображается список всех ссылок, настроенных в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="94feb-190">Для каждой ссылки отображается пропускная способность звука и видео.</span><span class="sxs-lookup"><span data-stu-id="94feb-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="94feb-191">Кроме того, отображается текущая полоса пропускания (в кбит/с и в процентах от емкости).</span><span class="sxs-lookup"><span data-stu-id="94feb-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="94feb-192">Инструмент использует цветовое кодирование для выделения ссылок, которые имеют близкое к емкости значение, позволяет администраторам быстро изолировать такие ссылки.</span><span class="sxs-lookup"><span data-stu-id="94feb-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-193">Если монитор службы политики пропускной способности испытывает сбой при подключении к любой из настроенных служб политики пропускной способности, информация в разделе сведения о <STRONG>компьютере</STRONG> и вкладки <STRONG>сведения о топологии</STRONG> не будут заполнены.</span><span class="sxs-lookup"><span data-stu-id="94feb-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="94feb-194">Тем не менее, средство может подключаться изначально, но при этом теряет соединение со службой.</span><span class="sxs-lookup"><span data-stu-id="94feb-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="94feb-195">В таких случаях администраторы могут видеть устаревшую информацию.</span><span class="sxs-lookup"><span data-stu-id="94feb-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="94feb-196">На каждой из вкладок имеется штамп времени <STRONG>последнего обновления</STRONG> , который позволяет администраторам просматривать время последнего обновления данных для конкретной службы политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="94feb-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-197">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-197">Output</span></span>

<span data-ttu-id="94feb-198">Отсутствует вывод командной строки; выходные данные программы хранятся в основном графическом интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-199">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-199">Purpose</span></span>

<span data-ttu-id="94feb-200">Средство мониторинга службы политики пропускной способности позволяет администраторам видеть состояние каждой службы политики пропускной способности, определенной в топологии.</span><span class="sxs-lookup"><span data-stu-id="94feb-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="94feb-201">Кроме того, администраторы могут видеть использование пропускной способности в режиме реального времени для всех ссылок, определенных в документе конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-202">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-202">Requirements</span></span>

<span data-ttu-id="94feb-203">Средство мониторинга службы политики пропускной способности необходимо запускать на компьютере, входящем в топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-204">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-204">Summary</span></span>

<span data-ttu-id="94feb-205">Монитор службы политики пропускной способности может быть ценным ресурсом для администраторов, чтобы они могли проверить состояние всех служб политики пропускной способности в топологии, и более важно — они могут получить использование пропускной способности в режиме реального времени для ссылок, определенных в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="94feb-206">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="94feb-207">Анализатор использования полосы пропускания — это средство, которое создает отчеты о различных режимах использования полосы пропускания в конечных точках UC по каналам глобальной сети в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="94feb-208">Эти отчеты можно использовать для ознакомления с текущей моделью потребления полосы пропускания и для планирования пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="94feb-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-209">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-209">Description</span></span>

<span data-ttu-id="94feb-210">Анализатор использования полосы пропускания реализуется как приложение, основанное на пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="94feb-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="94feb-211">Это средство создает отчеты специально для использования звука в сети и помогает при планировании мощности.</span><span class="sxs-lookup"><span data-stu-id="94feb-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="94feb-212">Кроме того, он выполняет итерацию по пропускной способности, назначенной различным каналам.</span><span class="sxs-lookup"><span data-stu-id="94feb-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-213">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-213">Output</span></span>

<span data-ttu-id="94feb-214">Анализатор использования полосы пропускания предоставляет графический показатель мощности и интенсивности пропускной способности для всех каналов глобальной сети, настроенных в системе.</span><span class="sxs-lookup"><span data-stu-id="94feb-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-215">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-215">Purpose</span></span>

<span data-ttu-id="94feb-216">В любом развертывании голосовых и видеофайлов очень важно отслеживать и оценить тенденцию использования пропускной способности трафика мультимедиа в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="94feb-217">Анализатор использования полосы пропускания позволяет администратору добиться всего этого.</span><span class="sxs-lookup"><span data-stu-id="94feb-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="94feb-218">Это средство выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="94feb-218">This tool does the following:</span></span>

  - <span data-ttu-id="94feb-219">Создает конкретные отчеты по использованию звука в сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="94feb-220">Способствует более эффективному планированию емкости и итерации по емкости полосы пропускания, назначенной различным связям</span><span class="sxs-lookup"><span data-stu-id="94feb-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="94feb-221">Анализатор использования полосы пропускания может создавать графические графики для отчетов о емкости и использовании полосы пропускания; они перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="94feb-222">Все связи WAN в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="94feb-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="94feb-223">Фильтрация по выбранным каналам глобальной сети</span><span class="sxs-lookup"><span data-stu-id="94feb-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="94feb-224">Фильтрация по каналам WAN с превышением установленной емкости канала</span><span class="sxs-lookup"><span data-stu-id="94feb-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="94feb-225">Фильтрация по каналам WAN с использованием подготовленной пропускной способности</span><span class="sxs-lookup"><span data-stu-id="94feb-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="94feb-226">Фильтрация по каналам WAN с достижением критических уровней (использование пропускной способности, превышающее 90% пропускной способности канала WAN)</span><span class="sxs-lookup"><span data-stu-id="94feb-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="94feb-227">Фильтрация по типу канала WAN — связи сайтов сети, взаимосвязи между регионами и ссылки на сайте</span><span class="sxs-lookup"><span data-stu-id="94feb-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="94feb-228">Фильтрация по области сети</span><span class="sxs-lookup"><span data-stu-id="94feb-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="94feb-229">Приложения</span><span class="sxs-lookup"><span data-stu-id="94feb-229">Applications</span></span>

<span data-ttu-id="94feb-230">Анализатор использования полосы пропускания использует следующие два приложения (инструменты):</span><span class="sxs-lookup"><span data-stu-id="94feb-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="94feb-231">**WanLinkLogCollector.exe**     Это средство позволяет пользователю вводить необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="94feb-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="94feb-232">**BandwidthUtilizationAnalyzer.xlsм**    WanLinkLogCollector.exe автоматически запускается отчет по электронной таблице Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="94feb-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="94feb-233">Это приложение позволяет пользователю применять фильтры к отчету, как показано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="94feb-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="94feb-234">Этапы использования анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="94feb-235">Использование анализатора использования полосы пропускания состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="94feb-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="94feb-236">Сбор журналов, который выполняется с помощью WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="94feb-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="94feb-237">Настройка отчетов, выполняемых с помощью BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="94feb-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94feb-238">Мы настоятельно рекомендуем вручную запускать BandwidthUtilizationAnalyzer.xlsm конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="94feb-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="94feb-239">Запуск анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="94feb-240">Запустите WanLinkLogCollector.exe из командной строки или с помощью проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="94feb-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="94feb-241">**Использование WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="94feb-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="94feb-242">Использование WanLinkLogCollector.exe состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="94feb-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="94feb-243">**Запись временной шкалы**     Укажите временную шкалу, для которой необходимо создать отчет.</span><span class="sxs-lookup"><span data-stu-id="94feb-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="94feb-244">**Указание каталогов файлов**     Предоставление сведений о расположении файлов</span><span class="sxs-lookup"><span data-stu-id="94feb-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="94feb-245">**Сбор журналов и запуск средства просмотра отчетов**    Выполнение команды для создания отчета</span><span class="sxs-lookup"><span data-stu-id="94feb-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="94feb-246">Шаг 1: запись временной шкалы</span><span class="sxs-lookup"><span data-stu-id="94feb-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="94feb-247">Ведение журнала временной шкалы позволяет пользователю средства указать следующие сведения, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="94feb-248">**Дата начала** Это Дата начала временной шкалы, для которой создается отчет; Например, 1 августа 2010 г.</span><span class="sxs-lookup"><span data-stu-id="94feb-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="94feb-249">**Дата окончания** Это Дата окончания временной шкалы, для которой создается отчет; Например, 30 сентября 2010 г.</span><span class="sxs-lookup"><span data-stu-id="94feb-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="94feb-250">![Начальная и конечная даты в использовании полосы пропускания A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Начальная и конечная даты в использовании полосы пропускания A")</span><span class="sxs-lookup"><span data-stu-id="94feb-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="94feb-251">Шаг 2. Указание каталогов файлов</span><span class="sxs-lookup"><span data-stu-id="94feb-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="94feb-252">Пользователь может указать следующие каталоги файлов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="94feb-253">**Расположение файлов журнала сервера** Расположение папки, в которой хранятся журналы сервера политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="94feb-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="94feb-254">Как правило, это \<fileserver\> \\ \<choice of FE\> \\ аппсерверфилес \\ PDP.</span><span class="sxs-lookup"><span data-stu-id="94feb-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="94feb-255">**Расположение хранилища временных файлов** Расположение временного файла, в котором хранятся промежуточные файлы во время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="94feb-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="94feb-256">![Каталоги файлов в анал использования полосы пропускания](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Каталоги файлов в анал использования полосы пропускания")</span><span class="sxs-lookup"><span data-stu-id="94feb-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-257">Обеспечьте достаточный доступ к файлам для журналов сервера и папку хранилища временных файлов для пользователя средства.</span><span class="sxs-lookup"><span data-stu-id="94feb-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="94feb-258">Шаг 3: сбор журналов и запуск средства просмотра отчетов</span><span class="sxs-lookup"><span data-stu-id="94feb-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="94feb-259">Для сбора журналов и запуска средства просмотра отчетов нажмите кнопку **выполнить** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="94feb-260">На этом этапе выполняется сбор необходимых данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-260">This step collects the required data.</span></span>

<span data-ttu-id="94feb-261">![Сбор данных в анали использования полосы пропускания](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Сбор данных в анали использования полосы пропускания")</span><span class="sxs-lookup"><span data-stu-id="94feb-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="94feb-262">После успешного выполнения проверки входного сообщения отображается приведенное ниже сообщение.</span><span class="sxs-lookup"><span data-stu-id="94feb-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="94feb-263">![Журнала собранных уведомлений в утили пропускной способности](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Журнала собранных уведомлений в утили пропускной способности")</span><span class="sxs-lookup"><span data-stu-id="94feb-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="94feb-264">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="94feb-264">Click **OK**.</span></span> <span data-ttu-id="94feb-265">BandwidthUtilizationAnalyzer.xlsm автоматически запускается.</span><span class="sxs-lookup"><span data-stu-id="94feb-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="94feb-266">Следуйте инструкциям в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="94feb-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="94feb-267">Дополнительные сведения приведены в разделе **Using BandwidthUtilizationAnalyzer.xlsm** в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="94feb-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="94feb-268">**Использование BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="94feb-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="94feb-269">Когда BandwidthUtilizationAnalyzer.xlsm автоматически запустится, нажмите кнопку **Обновить** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="94feb-270">![BandwidthUtilizationAnalyzer.xlsм](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsм")</span><span class="sxs-lookup"><span data-stu-id="94feb-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="94feb-271">При открытии папки файлов выберите consolidated.csv в расположении, указанном в окне сообщения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="94feb-272">В нем также указано расположение в формате **C: \\ TEMP**.</span><span class="sxs-lookup"><span data-stu-id="94feb-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="94feb-273">![Открытие папки в BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Открытие папки в BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="94feb-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="94feb-274">Нажмите кнопку **Импортировать**.</span><span class="sxs-lookup"><span data-stu-id="94feb-274">Click **Import**.</span></span>

4.  <span data-ttu-id="94feb-275">Графический график создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="94feb-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="94feb-276">Он доступен при исчезновении указателя рабочего стола в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="94feb-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="94feb-277">![Применение фильтров в представлении отчета.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Применение фильтров в представлении отчета.")</span><span class="sxs-lookup"><span data-stu-id="94feb-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="94feb-278">Применение фильтров к представлению отчета</span><span class="sxs-lookup"><span data-stu-id="94feb-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="94feb-279">Фильтры, которые можно применить к представлению отчета, как показано ниже, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="94feb-280">![Применение фильтров в представлении отчета.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Применение фильтров в представлении отчета.")</span><span class="sxs-lookup"><span data-stu-id="94feb-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="94feb-281">**Name (имя** ) Фильтрация по каналам WAN (фильтр находится в правой части диаграммы). Префикс указывает следующие типы ссылок; Ознакомьтесь с вертикальным (синим) полем:</span><span class="sxs-lookup"><span data-stu-id="94feb-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="94feb-282">**Сайт S** Связь WAN между сетевым сайтом и регионом сети</span><span class="sxs-lookup"><span data-stu-id="94feb-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="94feb-283">**Межсайтовый** Канал WAN между двумя сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="94feb-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="94feb-284">**Внутрихолдинговый** Канал WAN между двумя областями сети</span><span class="sxs-lookup"><span data-stu-id="94feb-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="94feb-285">**Превышено ограничение** Фильтрация по каналам глобальной сети, использование пропускной способности которых превышает емкость полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="94feb-286">**Критические уровни** Фильтрация по каналам глобальной сети, использование которых пропускной способности достигло 90% или превышает емкость полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="94feb-287">**Неиспользованный** Фильтрация по каналам глобальной сети, использование полосы пропускания которых было меньше 25% от емкости полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="94feb-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="94feb-288">**Тип ссылки** Фильтрация по следующим типам каналов WAN Links:</span><span class="sxs-lookup"><span data-stu-id="94feb-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="94feb-289">Тип **сетевого сайта**</span><span class="sxs-lookup"><span data-stu-id="94feb-289">**Network site** type</span></span>
    
      - <span data-ttu-id="94feb-290">Тип **межсайтового взаимодействия**</span><span class="sxs-lookup"><span data-stu-id="94feb-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="94feb-291">Тип **связи между регионами**</span><span class="sxs-lookup"><span data-stu-id="94feb-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="94feb-292">**Region (регион** ) Фильтрация по регионам сети</span><span class="sxs-lookup"><span data-stu-id="94feb-292">**Region** Filter by network region</span></span>

<span data-ttu-id="94feb-293">На следующих рисунках показаны ранее описанные фильтры.</span><span class="sxs-lookup"><span data-stu-id="94feb-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="94feb-294">Фильтрация по **имени**.</span><span class="sxs-lookup"><span data-stu-id="94feb-294">Filter by **Name**.</span></span> <span data-ttu-id="94feb-295">Выберите список ссылок, которые должны отображаться на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="94feb-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="94feb-296">![Фильтрация по имени в BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Фильтрация по имени в BandwidthUtilizationAnalyzer.")</span><span class="sxs-lookup"><span data-stu-id="94feb-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="94feb-297">Фильтрация по **превышению лимита**.</span><span class="sxs-lookup"><span data-stu-id="94feb-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="94feb-298">Выберите **true** , чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="94feb-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="94feb-299">![Фильтрация по превышению предельного значения.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Фильтрация по превышению предельного значения.")</span><span class="sxs-lookup"><span data-stu-id="94feb-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="94feb-300">Фильтрация по **критическим уровням**.</span><span class="sxs-lookup"><span data-stu-id="94feb-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="94feb-301">Выберите **true** , чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="94feb-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="94feb-302">![Фильтрация по критическим уровням.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Фильтрация по критическим уровням.")</span><span class="sxs-lookup"><span data-stu-id="94feb-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="94feb-303">Отфильтровать по **в разделе используется**.</span><span class="sxs-lookup"><span data-stu-id="94feb-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="94feb-304">Выберите **true** , чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="94feb-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="94feb-305">![Фильтрация по заданному принципу использования.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Фильтрация по заданному принципу использования.")</span><span class="sxs-lookup"><span data-stu-id="94feb-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="94feb-306">Фильтрация по **типу ссылки**.</span><span class="sxs-lookup"><span data-stu-id="94feb-306">Filter by **Link Type**.</span></span> <span data-ttu-id="94feb-307">Выберите тип или типы, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="94feb-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="94feb-308">![Фильтрация по типу ссылки.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Фильтрация по типу ссылки.")</span><span class="sxs-lookup"><span data-stu-id="94feb-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="94feb-309">Фильтрация по **регионам**.</span><span class="sxs-lookup"><span data-stu-id="94feb-309">Filter by **Region**.</span></span> <span data-ttu-id="94feb-310">Выберите список регионов, ссылки на которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="94feb-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="94feb-311">![Фильтрация по регионам.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Фильтрация по регионам.")</span><span class="sxs-lookup"><span data-stu-id="94feb-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-312">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-312">Requirements</span></span>

  - <span data-ttu-id="94feb-313">Платформа .NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="94feb-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="94feb-314">Microsoft Excel 2010 или Excel 2007</span><span class="sxs-lookup"><span data-stu-id="94feb-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-315">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-315">Summary</span></span>

<span data-ttu-id="94feb-316">Анализатор использования полосы пропускания используется для отображения использования пропускной способности звука для трафика UC в сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="94feb-317">Это средство можно использовать для отправки отчетов об использовании пропускной способности видео в сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="94feb-318">Вызов Parkometer</span><span class="sxs-lookup"><span data-stu-id="94feb-318">Call Parkometer</span></span>

<span data-ttu-id="94feb-319">Call Parkometer — это приложение командной строки, предоставляющее простой доступ к базе данных орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="94feb-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-320">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-320">Description</span></span>

<span data-ttu-id="94feb-321">Parkometer вызовов — это средство для отслеживания приостановленных звонков в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="94feb-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="94feb-322">Он также собирает статистику по орбитам и использованию сервера парковки вызовов (CPS).</span><span class="sxs-lookup"><span data-stu-id="94feb-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="94feb-323">Это средство командной строки предоставляет доступ для чтения и записи к базе данных SQL Server орбиты CPS с локального или удаленного подключенного компьютера.</span><span class="sxs-lookup"><span data-stu-id="94feb-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="94feb-324">Все параметры являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="94feb-324">All options are mutually exclusive.</span></span> <span data-ttu-id="94feb-325">Синтаксис командной строки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94feb-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="94feb-326">параметр **– o** содержит список всех диапазонов орбиты, настроенных для этого пула.</span><span class="sxs-lookup"><span data-stu-id="94feb-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="94feb-327">**– n** параметр — отображает список всех используемых в настоящее время орбит в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="94feb-328">Отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="94feb-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="94feb-329">Универсальный код ресурса (URI) SIP и паркующего;.</span><span class="sxs-lookup"><span data-stu-id="94feb-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="94feb-330">Имя узла сервера публикаций Contribute, в котором приостановлен звонок.</span><span class="sxs-lookup"><span data-stu-id="94feb-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="94feb-331">Метка времени приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="94feb-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="94feb-332">параметр **– f** — отображает число свободных орбит в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="94feb-333">\*\*– r \<n\> \*\* параметр — перечисляет \<n\> последние приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="94feb-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="94feb-334">Отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="94feb-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="94feb-335">Универсальный код ресурса SIP SIP.</span><span class="sxs-lookup"><span data-stu-id="94feb-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="94feb-336">URI SIP паркующего;.</span><span class="sxs-lookup"><span data-stu-id="94feb-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="94feb-337">Имя узла сервера публикаций Contribute, в котором был приостановлен вызов.</span><span class="sxs-lookup"><span data-stu-id="94feb-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="94feb-338">Метка времени получения или удаления вызова.</span><span class="sxs-lookup"><span data-stu-id="94feb-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="94feb-339">\*\*— t \<n\> \*\* параметр — тестирует резервирование орбиты в базе данных для отображения случайных чисел назначенных орбит.</span><span class="sxs-lookup"><span data-stu-id="94feb-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-340">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-340">Output</span></span>

<span data-ttu-id="94feb-341">В зависимости от входных параметров, указанных в командной строке, вызовите Parkometer отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="94feb-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="94feb-342">Все диапазоны орбит, настроенные для этого пула</span><span class="sxs-lookup"><span data-stu-id="94feb-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="94feb-343">Приостановленные звонки</span><span class="sxs-lookup"><span data-stu-id="94feb-343">Currently parked calls</span></span>

  - <span data-ttu-id="94feb-344">Количество свободных (доступных) орбит</span><span class="sxs-lookup"><span data-stu-id="94feb-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="94feb-345">Недавно приостановленные звонки</span><span class="sxs-lookup"><span data-stu-id="94feb-345">Recently parked calls</span></span>

  - <span data-ttu-id="94feb-346">Зарезервированные орбиты для тестирования единообразных и случайных значений орбиты</span><span class="sxs-lookup"><span data-stu-id="94feb-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-347">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-347">Purpose</span></span>

<span data-ttu-id="94feb-348">Средство CPS предназначено для предоставления доступа к базе данных CPS с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="94feb-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="94feb-349">Администратор может просматривать использование CPS и определять число орбит, назначенных пулу.</span><span class="sxs-lookup"><span data-stu-id="94feb-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-350">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-350">Requirements</span></span>

<span data-ttu-id="94feb-351">Если это средство запущено на том же компьютере, где установлен сервер публикаций Contribute, никаких требований не существует.</span><span class="sxs-lookup"><span data-stu-id="94feb-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="94feb-352">Если это средство запущено на удаленном компьютере, то база данных SQL Server, используемая Lync Server 2013, должна быть настроена на разрешение удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="94feb-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="94feb-353">Для подключения к SQL Server с помощью Parkometer вызовов необходимо настроить строку подключения к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="94feb-354">Эта строка подключения к базе данных SQL Server определена в файле конфигурации **parkometer.exe.config**. Он должен размещаться в том же каталоге, где находится parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="94feb-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="94feb-355">Приведенный ниже XML-файл является примером parkometer.exe.config. Параметры, которые необходимо настроить — это имя пользователя (например, администратора mydomain \\ ), пароль (например, мипассворд) и имя узла (например, MyServer).</span><span class="sxs-lookup"><span data-stu-id="94feb-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

## <a name="examples"></a><span data-ttu-id="94feb-356">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-356">Examples</span></span>

<span data-ttu-id="94feb-357">Развернутые диапазоны орбиты: параметр – o содержит список всех диапазонов орбиты, настроенных для этого пула, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="94feb-358">![Диапазоны орбиты в вызове Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Диапазоны орбиты в вызове Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="94feb-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="94feb-359">В настоящее время приостановленные звонки: параметр – n перечисляет все используемые на данный момент орбиты на этом пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="94feb-360">![Приостановленные вызовы в Parkometer вызовов.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Приостановленные вызовы в Parkometer вызовов.")</span><span class="sxs-lookup"><span data-stu-id="94feb-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="94feb-361">Число свободных орбит: параметр – f содержит число свободных орбит в пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="94feb-362">![Свободные орбиты в вызове Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Свободные орбиты в вызове Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="94feb-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="94feb-363">Недавно приостановленные звонки: параметр – r \<n\> содержит \<n\> последние приостановленные звонки, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="94feb-364">![Недавно припаркованные вызовы в вызове Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Недавно припаркованные вызовы в вызове Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="94feb-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="94feb-365">Протестируйте резервирование орбиты: параметр – t тестирует резервирование \<n\> орбиты в базе данных, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="94feb-366">![Протестируйте резервирование орбит в Parkometer вызовов.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Протестируйте резервирование орбит в Parkometer вызовов.")</span><span class="sxs-lookup"><span data-stu-id="94feb-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-367">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-367">Summary</span></span>

<span data-ttu-id="94feb-368">Call Parkometer — это средство командной строки, предоставляющее подробные сведения о сервере парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="94feb-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="94feb-369">клеанупсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="94feb-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="94feb-370">Средство Клеанупсторажесервицедата Resource Kit позволяет удалять потерянные данные из базы данных, используемой службой хранилища Lync Server (LYSS).</span><span class="sxs-lookup"><span data-stu-id="94feb-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="94feb-371">Одной из функций службы хранения является буферизация связи между Lync Server и различных конечных конечных точек хранения данных, таких как SQL Server и Exchange.</span><span class="sxs-lookup"><span data-stu-id="94feb-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-372">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-372">Description</span></span>

<span data-ttu-id="94feb-373">Для поддержки высокого уровня доступности LYSS принимает и сохраняет копии данных на нескольких серверах переднего плана в пуле, а затем удаляет эти данные после доставки в последнее долговременное место хранения.</span><span class="sxs-lookup"><span data-stu-id="94feb-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="94feb-374">Существуют необычные ситуации, которые могут возникать в обычном режиме, когда сервер может перестать работать, а некоторые данные не будут очищаться должным образом.</span><span class="sxs-lookup"><span data-stu-id="94feb-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="94feb-375">Эти данные безвредны, но потребляют ограниченные ресурсы для обработки.</span><span class="sxs-lookup"><span data-stu-id="94feb-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="94feb-376">Значительная часть нормального обслуживания данных автоматизирована, но это средство позволяет безопасно идентифицировать и удалить такие потерянные данные при невозможности автоматического удаления.</span><span class="sxs-lookup"><span data-stu-id="94feb-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="94feb-377">Использование этого средства указывается, когда вызывается оповещение System Center Operations Manager (SCOM), в котором администратору предлагается удалить ненужные данные из локальных баз данных LYSS в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="94feb-378">В журнале событий на интерфейсном сервере, вызвавшем оповещение, будет соответствующее событие.</span><span class="sxs-lookup"><span data-stu-id="94feb-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="94feb-379">В сведениях о событии будут содержаться сведения о количестве потерянных данных, содержащихся в интерфейсе, и возникает, когда эти данные превышают пороговые значения, предварительно определяющие их.</span><span class="sxs-lookup"><span data-stu-id="94feb-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-380">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-380">Requirements</span></span>

<span data-ttu-id="94feb-381">Установите средства набора ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="94feb-382">Средство запускается на подключенных к домену компьютерах, где установлены сервер Lync Server и Командная консоль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="94feb-383">Средство использует командлет из командной консоли для определения всех серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="94feb-384">Во вторых случаях средство необходимо запускать на компьютере в пуле, где установлена база данных **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="94feb-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="94feb-385">Эта база данных используется средством Клеанупсторажесервицедата для получения сведений о подключении, необходимых для связи со службой маршрутизации Lync Server. Наконец, учетная запись или учетные данные, вызывающие средство, должны иметь разрешение на чтение и запись в файловый ресурс, на который они записываются в журнал вывода. Кроме того, это средство зависит от пула в стабильном состоянии.</span><span class="sxs-lookup"><span data-stu-id="94feb-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="94feb-386">По сути это означает, что все серверы переднего плана должны быть запущены и запущены, а экземпляр SQL Server ЛИНКЛОКАЛ и база данных LYSS должны быть подключены к, а у каждой группы маршрутизации должен быть полный набор из 1 основных серверов переднего плана и 2 дополнительных серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="94feb-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-387">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-387">Examples</span></span>

<span data-ttu-id="94feb-388">C: \\ Program Files \\ Microsoft Lync Server 2013 \\ ResKit \\ сторажесервице \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="94feb-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

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

## <a name="dbanalyze"></a><span data-ttu-id="94feb-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="94feb-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-390">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-390">Description</span></span>

<span data-ttu-id="94feb-391">DBAnalyze — это средство командной строки, помогающее администраторам собирать отчеты анализа о базах данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="94feb-392">В DBAnalyze имеются следующие режимы: диагностика, данные пользователей, конференц-связи, MCUs и фрагментация дисков:</span><span class="sxs-lookup"><span data-stu-id="94feb-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="94feb-393">**Диагностический режим**     Создает отчет, содержащий сведения о таблицах (число записей, фрагментация, размер данных и размер индекса). размеры файлов данных и журналов, время последнего резервного копирования связи между серверами, на которых работает Microsoft Office Communications Server, среднее число разрешений, контактов, контейнеров, подписок, публикаций, конечных точек на пользователя, неправильное размещение пользователей, пользователей, которые не могут маршрутизироваться, среднее количество конференций для каждого пользователя, запланированных конференций, активных конференций и версии базы данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94feb-394">Выполнение диагностического режима может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="94feb-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="94feb-395">**Режим**   данных пользователя Сообщает сведения о контактах, контейнерах, подписках, публикациях, разрешениях и группах контактов для указанного пользователя или для пользователей, имеющих этого пользователя в списках контактов и разрешений.</span><span class="sxs-lookup"><span data-stu-id="94feb-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="94feb-396">В этом режиме также выводится сводная информация о конференциях, на которые пользователь организует или приглашает.</span><span class="sxs-lookup"><span data-stu-id="94feb-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="94feb-397">**Режим конференции**     Сообщает подробные данные о конкретной конференции, в том числе сведения о времени расписания для Конференции, список приглашений, список типов мультимедиа, разрешенных для Конференции, активные MCUs (единицы управления MultiPoint), список активных участников и состояние сигналов каждого участника.</span><span class="sxs-lookup"><span data-stu-id="94feb-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="94feb-398">**Расшифровка идентификатора собрания**    Декодирует идентификатор собрания для телефонной сети общего пользования (PSTN), указанный с помощью коммутатора **/pstnid** , но не подключается к внутреннему серверу для получения подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="94feb-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="94feb-399">**Разрешение конференции**     Декодирует идентификатор собрания PSTN, указанный с помощью параметра **/pstnid** , и отображает сведения о конференции, указанной идентификатором.</span><span class="sxs-lookup"><span data-stu-id="94feb-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="94feb-400">**Режим MCUs**    Сообщает идентификатор, тип мультимедиа, URL-адрес, состояние пульса, нагрузку на конференцию и загрузку участников для каждого MCU в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="94feb-401">Режим фрагментации **диска**    Отображает состояние фрагментации всех дисков.</span><span class="sxs-lookup"><span data-stu-id="94feb-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="94feb-402">Это средство можно использовать для диагностики различных проблем или для оказания помощи администратору по планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="94feb-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="94feb-403">Например, если большинство пользователей, размещенных на сервере A, выбирают пользователей, размещенных на сервере б, в качестве их контактов, администратор может переместить пользователей на сервер а на сервер б, чтобы уменьшить трафик между серверами.</span><span class="sxs-lookup"><span data-stu-id="94feb-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-404">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-404">Output</span></span>

<span data-ttu-id="94feb-405">Это средство выводит предопределенные отчеты о базе данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="94feb-406">**Путь:** % ProgramFiles% \\ Microsoft Lync Server 2013 \\ reskit</span><span class="sxs-lookup"><span data-stu-id="94feb-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-407">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-407">Purpose</span></span>

<span data-ttu-id="94feb-408">Чтобы установить Dbanalyze.exe, скопируйте его в локальную папку и запустите средство.</span><span class="sxs-lookup"><span data-stu-id="94feb-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="94feb-409">Чтобы использовать средство, выполните приведенную ниже команду в командной строке.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="94feb-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="94feb-410">Ниже приведены описания параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="94feb-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="94feb-411">![Параметры командной строки для Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Параметры командной строки для Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="94feb-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-412">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-412">Requirements</span></span>

<span data-ttu-id="94feb-413">**Computer (компьютер** ) DBAnalyze можно запускать только с компьютера, присоединенного к домену, на котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="94feb-414">**Network (сеть** ) Компьютер должен иметь возможность подключения к серверной базе данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="94feb-415">**Программное обеспечение** Перед запуском DBAnalyze необходимо установить компоненты программного обеспечения Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="94feb-416">**Users (пользователи** ) В приведенной ниже таблице указаны администраторы, у которых есть необходимые разрешения на доступ к базам данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="94feb-417">![Таблица Permissions для Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Таблица Permissions для Dbanalyze.exe.")</span><span class="sxs-lookup"><span data-stu-id="94feb-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-418">Локальная учетная запись администратора необходима для <STRONG>/Report: режим диска</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="94feb-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-419">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-419">Examples</span></span>

<span data-ttu-id="94feb-420">Ниже приведены примеры допустимых Dbanalyze.exeных команд:</span><span class="sxs-lookup"><span data-stu-id="94feb-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-421">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-421">Summary</span></span>

<span data-ttu-id="94feb-422">Дбанализер предоставляет администраторам быстрые и простые для анализа баз данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="94feb-423">импортсторажесервицедата</span><span class="sxs-lookup"><span data-stu-id="94feb-423">ImportStorageServiceData</span></span>

<span data-ttu-id="94feb-424">Средство Импортсторажесервицедата Resource Kit позволяет повторно импортировать данные очередей и конечных точек, которые были удалены из службы хранения (LYSS), обратно в службу хранения.</span><span class="sxs-lookup"><span data-stu-id="94feb-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-425">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-425">Description</span></span>

<span data-ttu-id="94feb-426">Данные, удаляемые из службы хранилища, могли быть автоматически (периодически) на основе состояния элемента очереди или размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="94feb-427">Это могло произойти из-за вызова командлета отработки отказа пула вручную или командлета Сторажесервицефуллфлуш (который вызывается командлетом отработки отказа пула).</span><span class="sxs-lookup"><span data-stu-id="94feb-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="94feb-428">Обратите внимание, что в идеале данные не будут повторно импортироваться, если размер базы данных службы хранения (LYSS) на интерфейсных серверах переднего плана находится выше обычного уровня, так как это может привести к тому, что все данные будут экспортированы обратно. Кроме того, все проблемы, которые могут возникать при возникновении ошибок при увеличении очереди службы хранения, должны быть решены (например, ошибки конечной точки Exchange, проблемы с сетью или другие проблемы).</span><span class="sxs-lookup"><span data-stu-id="94feb-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="94feb-429">**Сценарий 1:** при отработке отказа пула файлы могут удаляться из службы хранилища для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="94feb-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="94feb-430">После завершения отработки отказа необходимо запустить средство для повторного импорта данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="94feb-431">**Сценарий 2:** данные очищаются автоматически каждый день или в ответ на базу данных службы хранилища, превышающие определенные пороговые значения размера (например, 60%, 80%, 90% Full).</span><span class="sxs-lookup"><span data-stu-id="94feb-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="94feb-432">Эти автоматически удаляемые данные должны повторно импортироваться администратором регулярно.</span><span class="sxs-lookup"><span data-stu-id="94feb-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="94feb-433">В приведенной выше ситуации, если пакет мониторинга SCOM не развернут, существуют события для службы хранилища Lync Server, связанные с очисткой данных из службы хранилища.</span><span class="sxs-lookup"><span data-stu-id="94feb-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="94feb-434">Идентификаторы событий 32075 (операция полного сброса начинается), 32076 (полная очистка завершена), 32082 (начато копирование на уровне обслуживания), 32083 (очистка на уровне обслуживания завершена), 32089 (очистка выполнена из-за заполнения базы данных).</span><span class="sxs-lookup"><span data-stu-id="94feb-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="94feb-435">Обратите внимание, что эти коды событий соответствуют выпуску RTM.</span><span class="sxs-lookup"><span data-stu-id="94feb-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="94feb-436">Когда администратор видит эти события, это означает, что существуют файлы, которые были удалены. Эти данные следует регулярно импортировать обратно с помощью этого средства, например один раз в неделю.</span><span class="sxs-lookup"><span data-stu-id="94feb-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="94feb-437">При выпуске веб-службы при развертывании средства мониторинга работоспособности пакета SCOM для Lync Server появляются новые оповещения, которые попросите администратора повторно импортировать удаляемые данные обратно в службу хранилища.</span><span class="sxs-lookup"><span data-stu-id="94feb-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="94feb-438">В журнале событий на сервере переднего плана, вызвавшем оповещение, появится соответствующее событие.</span><span class="sxs-lookup"><span data-stu-id="94feb-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="94feb-439">Событие предоставит описание родительского пути, в котором находятся файлы данных с очисткой, а также количество файлов, соответствующих условиям оповещения.</span><span class="sxs-lookup"><span data-stu-id="94feb-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="94feb-440">Критерий оповещения состоит в том, что существует X или более файлов по отношению к определенному родительскому пути по крайней мере по крайней мере по крайней мере по оси Y дней (где X и Y задаются в Сторажесервице, но их можно переопределить, изменив файл АППКОНФИГ). Два примера событий, которые могут вызывать оповещение о работоспособности, показаны ниже, а их родительский путь отличается.</span><span class="sxs-lookup"><span data-stu-id="94feb-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="94feb-441">Один из возможных вариантов — файловый ресурс веб-службы, а другая возможность — локальный каталог данных приложений для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="94feb-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="94feb-442">(например, c: \\ Програмдата \\ Microsoft \\ Lync Server \\ сторажесервице).</span><span class="sxs-lookup"><span data-stu-id="94feb-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="94feb-443">После этого администратор запустит это средство reskit.</span><span class="sxs-lookup"><span data-stu-id="94feb-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="94feb-444">Это средство увеличит нагрузку ЦП и ввода-вывода на интерфейсном сервере, на котором она работает, а также на других интерфейсных серверах, в случае, если данные не принадлежат внешнему интерфейсу, на котором выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="94feb-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="94feb-445">Мы рекомендуем запускать это средство, если на интерфейсных серверах не загружается высокая загрузка ЦП и ввода-вывода, например, в нерабочее время.</span><span class="sxs-lookup"><span data-stu-id="94feb-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="94feb-446">Во вторых, это средство может выполнить из 2 до 3 минут, чтобы импортировать один файл данных.</span><span class="sxs-lookup"><span data-stu-id="94feb-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="94feb-447">Помните об этом при оценке времени, в течение которого будет выполняться средство. Подробный файл журнала, создаваемый средством, по умолчанию отображается в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="94feb-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="94feb-448">Удалите его, если нет сообщений об ошибках, так как файл журнала может содержать не более десятков МБ.</span><span class="sxs-lookup"><span data-stu-id="94feb-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="94feb-449">![События журнала событий для хранилища событий сервера.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "События журнала событий для хранилища событий сервера.")</span><span class="sxs-lookup"><span data-stu-id="94feb-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-450">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-450">Requirements</span></span>

<span data-ttu-id="94feb-451">Установите средства набора ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="94feb-452">Средство запускается на подключенных к домену компьютерах, где установлены Lync Server и Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="94feb-453">Средство использует командлет из командной консоли, чтобы определить все серверы переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="94feb-454">Во вторых случаях средство необходимо запускать на компьютере в пуле, где установлена база данных **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="94feb-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="94feb-455">Эта база данных используется средством для получения расположения общего файлового ресурса WEBSERVICE для пула. Кроме того, перед использованием средства каждый сервер переднего плана должен сначала включить удаленное взаимодействие Windows PowerShell с помощью командлета **Enable-псремотинг** на каждом сервере переднего плана, а также на компьютере, с которого выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="94feb-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="94feb-456">В противном случае удаленные команды Windows PowerShell из этого средства завершатся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="94feb-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="94feb-457">Удаленное взаимодействие Windows PowerShell может быть отключено на всех серверах переднего плана в пуле после его завершения.</span><span class="sxs-lookup"><span data-stu-id="94feb-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="94feb-458">Наконец, учетная запись или учетные данные, вызывающие средство, должны иметь разрешение на чтение и запись для общего файлового ресурса WebService для пула, в котором выполняется это средство.</span><span class="sxs-lookup"><span data-stu-id="94feb-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="94feb-459">В противном случае средство завершится с ошибками разрешений ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="94feb-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-460">В Windows Server 2012 удаленное взаимодействие Windows PowerShell включено по умолчанию, но не в операционной системе Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="94feb-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-461">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-461">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="94feb-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="94feb-462">LCSSync</span></span>

<span data-ttu-id="94feb-463">Средство LCSSync помогает развернуть программное обеспечение Lync Server 2013 для связи в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="94feb-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="94feb-464">Это средство используется для синхронизации пользователей и групп из различных лесов пользователя как объект контакта доменных служб Active Directory в центральном лесу, где установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-465">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-465">Description</span></span>

<span data-ttu-id="94feb-466">LCSSync использует синхронизированные объекты контактов доменных служб Active Directory в центральном лесу, чтобы разрешить пользователям Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="94feb-467">Для предоставления единого входа основная учетная запись пользователя должна быть сопоставлена с объектом контакта доменных служб Active Directory в центральном лесу для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="94feb-468">Это средство помогает выполнить это сопоставление.</span><span class="sxs-lookup"><span data-stu-id="94feb-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="94feb-469">Это средство предоставляет шаблоны для создания агентов управления на сервере Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-470">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-470">Summary</span></span>

<span data-ttu-id="94feb-471">Средство LCSSync помогает развернуть Lync Server в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="94feb-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="94feb-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="94feb-472">LookupUserConsole</span></span>

<span data-ttu-id="94feb-473">Средство LookupUserConsole отображает внутреннюю информацию маршрутизации Lync Server о конкретных пользователях.</span><span class="sxs-lookup"><span data-stu-id="94feb-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="94feb-474">Эта информация может быть полезной для поддержки корпорацией Майкрософт личных сведений при диагностике проблем развертывания и маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="94feb-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-475">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-475">Description</span></span>

<span data-ttu-id="94feb-476">При выполнении LookupUserConsole.exe откроется Командная строка, которая принимает адреса SIP и пытается отобразить внутреннюю информацию маршрутизации Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="94feb-477">Введите **Exit** , чтобы завершить работу средства LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="94feb-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-478">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-478">Requirements</span></span>

<span data-ttu-id="94feb-479">Установите средства набора ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="94feb-480">Средство запускается на подключенных к домену компьютерах, на которых установлен Lync Server</span><span class="sxs-lookup"><span data-stu-id="94feb-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-481">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-481">Examples</span></span>

<span data-ttu-id="94feb-482">C: \\ программные файлы \\ Microsoft Lync Server 2013 \\ ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="94feb-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="94feb-483">мстурнпинг</span><span class="sxs-lookup"><span data-stu-id="94feb-483">MsTurnPing</span></span>

<span data-ttu-id="94feb-484">Средство Мстурнпинг позволяет администратору программного обеспечения Microsoft Lync Server 2013 Communications проверить состояние серверов с пограничными аудио-и видеоданными, а также серверами, на которых работают службы политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="94feb-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-485">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-485">Description</span></span>

<span data-ttu-id="94feb-486">Средство Мстурнпинг позволяет администратору Lync Server 2013 Communications Server проверять состояние серверов с пограничными аудио-и видеоданными, а также серверами, на которых работают службы политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="94feb-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="94feb-487">Средство позволяет администратору выполнять следующие тесты:</span><span class="sxs-lookup"><span data-stu-id="94feb-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="94feb-488">Тест пограничного сервера аудио-и видеоданных: средство выполняет тестирование для всех пограничных серверов аудио-и видеоданных в топологии, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="94feb-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="94feb-489">Проверка того, что служба проверки подлинности на Lync Server запущена и может выдать правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="94feb-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="94feb-490">Проверка того, что служба аудио-и видеоданных Lync Server запущена и может успешно выделить ресурсы на внешнем пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="94feb-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="94feb-491">Проверка службы политики пропускной способности: средство выполняет тесты для всех серверов, на которых выполняются службы политики пропускной способности в топологии, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="94feb-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="94feb-492">Проверка того, что служба политики пропускной способности Lync Server (проверка подлинности) запущена и может выдать правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="94feb-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="94feb-493">Проверка того, что запущена служба политики пропускной способности Lync Server (ядро), и может пройти проверку пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="94feb-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="94feb-494">Это средство необходимо запускать на компьютере, который входит в топологию и на котором установлено локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="94feb-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-495">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-495">Output</span></span>

<span data-ttu-id="94feb-496">Средство выводит результаты каждой операции.</span><span class="sxs-lookup"><span data-stu-id="94feb-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="94feb-497">Если выполняется тест **аудиовидеоеджесервер** , выводятся следующие данные средства:</span><span class="sxs-lookup"><span data-stu-id="94feb-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="94feb-498">Результаты тестирования компьютеров, которые обеспечивают службу проверки подлинности Lync Server аудио-и видео в топологии</span><span class="sxs-lookup"><span data-stu-id="94feb-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="94feb-499">Результаты тестирования компьютеров, которые обеспечивают службу аудио-и видеосвязи Lync Server в топологии</span><span class="sxs-lookup"><span data-stu-id="94feb-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="94feb-500">Если выполняется тест **бандвидсполицисервер** , выводятся следующие данные средства:</span><span class="sxs-lookup"><span data-stu-id="94feb-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="94feb-501">Результаты тестирования компьютеров, которые обеспечивают службу политики пропускной способности Lync Server (проверка подлинности) в топологии</span><span class="sxs-lookup"><span data-stu-id="94feb-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="94feb-502">Результаты тестирования компьютеров, которые обеспечивают службу политики пропускной способности Lync Server (ядро) в топологии</span><span class="sxs-lookup"><span data-stu-id="94feb-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-503">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-503">Requirements</span></span>

  - <span data-ttu-id="94feb-504">Это средство необходимо запускать на компьютере, который находится в топологии и имеет локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="94feb-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="94feb-505">Средство должно быть запущено от имени администратора, имеющего доступ к локальному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="94feb-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-506">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-506">Examples</span></span>

<span data-ttu-id="94feb-507">Ниже приведен пример входных данных средства.</span><span class="sxs-lookup"><span data-stu-id="94feb-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-508">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-508">Summary</span></span>

<span data-ttu-id="94feb-509">Это средство может быть ценным ресурсом для администраторов Lync Server 2013, которые хотят проверить состояние серверов, на которых работают службы политики аудио-и видеосвязи и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="94feb-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="94feb-510">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="94feb-510">Network Configuration Viewer</span></span>

<span data-ttu-id="94feb-511">С помощью средства просмотра конфигурации сети администраторы программного обеспечения Microsoft Lync Server 2013 могут просматривать топологию сети контроля допуска звонков (CAC) для предприятия, подготовленного к использованию сеансов связи в режиме реального времени, таких как голосовые или видеовызовы на основе указанной емкости полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="94feb-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="94feb-512">Lync Server 2013 администраторы определяют политики CAC, которые применяются службами политики пропускной способности, устанавливаемыми с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-513">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-513">Description</span></span>

<span data-ttu-id="94feb-514">Средство просмотра конфигурации сети (NetworkConfigurationViewer.exe) позволяет администраторам выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="94feb-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="94feb-515">Загрузка и просмотр топологии сети CAC из развертывания Lync Server 2013 в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="94feb-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="94feb-516">Загрузка и просмотр топологии сети CAC из файла журнала сервера политики пропускной способности в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="94feb-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="94feb-517">Сохраните и сохраните топологию сети CAC в формате XML на диске.</span><span class="sxs-lookup"><span data-stu-id="94feb-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="94feb-518">Сохраните и сохраните схему топологии сети CAC в формате JPG или BMP.</span><span class="sxs-lookup"><span data-stu-id="94feb-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="94feb-519">Просмотр данных конфигурации топологии сети CAC.</span><span class="sxs-lookup"><span data-stu-id="94feb-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="94feb-520">Просмотр топологии сети CAC в стиле представления дерева.</span><span class="sxs-lookup"><span data-stu-id="94feb-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="94feb-521">Определите настраиваемые соединители для связей топологии сети CAC (например, "сайт-регион", "между регионами" и "между сайтами").</span><span class="sxs-lookup"><span data-stu-id="94feb-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="94feb-522">Просмотр сведений о сайте топологии сети CAC, сведений о регионе и о подготовленных политиках пропускной способности и сетевых соединениях.</span><span class="sxs-lookup"><span data-stu-id="94feb-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-523">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-523">Purpose</span></span>

<span data-ttu-id="94feb-524">Просмотр ссылок на топологию сети CAC в графическом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="94feb-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-525">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-525">Examples</span></span>

<span data-ttu-id="94feb-526">**Загрузка и просмотр топологии сети CAC из развертывания Lync Server 2013 в графическом формате:** Lync Server 2013 администраторы могут загружать и просматривать конфигурацию топологии сети CAC на любом компьютере с Lync Server 2013, используя параметр **конфигурации сети** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="94feb-527">Средство не сможет скачать или просмотреть такую конфигурацию при развертывании на компьютере, на котором нет подключения к хранилищу конфигураций Lync.</span><span class="sxs-lookup"><span data-stu-id="94feb-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="94feb-528">![Загрузка конфигурации сети.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Загрузка конфигурации сети.")</span><span class="sxs-lookup"><span data-stu-id="94feb-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="94feb-529">**Загрузка и просмотр топологии сети CAC из файла журнала сервера политики пропускной способности в графическом формате:** Серверы политики пропускной способности Lync Server 2013. Сохраните топологию сети CAC в качестве части механизма ведения журнала в расположении общего файлового ресурса Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="94feb-530">Администраторы Lync Server могут просматривать такой файл в графическом формате с помощью параметра **Конфигурация Open Network** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="94feb-531">![Открытие файла журнала сервера политики пропускной способности.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Открытие файла журнала сервера политики пропускной способности.")</span><span class="sxs-lookup"><span data-stu-id="94feb-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="94feb-532">Сохраните и сохраните топологию сети CAC в формате XML на диске: Lync Server 2013 администраторы могут сохранить файл конфигурации топологии сети CAC в формате XML с помощью параметра **сохранить копию конфигурации сети** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="94feb-533">Сохраненный файл конфигурации можно использовать в автономном режиме для просмотра в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="94feb-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="94feb-534">![Сохранение конфигурации сети в виде XML-файла.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Сохранение конфигурации сети в виде XML-файла.")</span><span class="sxs-lookup"><span data-stu-id="94feb-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="94feb-535">Сохранение и **Сохранение схемы топологии** сети CAC в формате JPG или BMP: Lync Server 2013 администраторы могут сохранить конфигурацию ТОПОЛОГИИ сети CAC в графическом формате (форматы файлов JPG и BMP), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="94feb-536">![Сохранение конфигурации сети как изображения.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Сохранение конфигурации сети как изображения.")</span><span class="sxs-lookup"><span data-stu-id="94feb-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="94feb-537">**Просмотр данных конфигурации топологии сети CAC:** Lync Server 2013 администраторы могут просматривать связанные данные конфигурации сети, такие как регионы сети, сетевые сайты, профили пропускной способности и IP-адреса подсетей сайтов в текстовом формате, с помощью параметра Просмотр данных конфигурации сети, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="94feb-538">![Просмотр данных конфигурации сети.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Просмотр данных конфигурации сети.")</span><span class="sxs-lookup"><span data-stu-id="94feb-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="94feb-539">**Просмотр топологии сети CAC в стиле представления дерева:** Lync Server 2013 администраторы могут просматривать связанные данные конфигурации сети в графическом стиле представления дерева, используя панель управления в левой части окна инструментов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="94feb-540">![Просмотр данных конфигурации сети в виде дерева.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Просмотр данных конфигурации сети в виде дерева.")</span><span class="sxs-lookup"><span data-stu-id="94feb-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="94feb-541">**Определите настраиваемые соединители для связей топологии сети CAC (например, "сайт-регион", "между регионами" и "сеть-сеть"):** Lync Server 2013 администраторы могут определять настраиваемые графические соединители для каналов связи WAN с настройкой сети с помощью параметра Settings, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="94feb-542">Это позволяет отличать различные типы сетевых связей, подготовленных в конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="94feb-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="94feb-543">![Определение настраиваемых соединителей для топологии сети CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Определение настраиваемых соединителей для топологии сети CAC")</span><span class="sxs-lookup"><span data-stu-id="94feb-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="94feb-544">**Просмотр сведений о сайте топологии сети CAC, сведений о регионе и подготовленных политиках пропускной способности:** Lync Server 2013 администраторы могут просматривать связанные сведения о области сети CAC, сведения о сайте и сведения о подготовке пропускной способности CAC с помощью параметров, показанных ниже.</span><span class="sxs-lookup"><span data-stu-id="94feb-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="94feb-545">(Например, щелкните **сведения** в сетевом регионе или в объекте сетевого сайта.)</span><span class="sxs-lookup"><span data-stu-id="94feb-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="94feb-546">![Определение настраиваемых соединителей для сети;](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Определение настраиваемых соединителей для сети;")</span><span class="sxs-lookup"><span data-stu-id="94feb-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-547">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-547">Summary</span></span>

<span data-ttu-id="94feb-548">Это средство может быть ценным ресурсом для администраторов Lync Server 2013, которые хотят просмотреть топологию сети CAC для развертывания в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="94feb-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="94feb-549">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="94feb-549">Response Group Agent Live</span></span>

<span data-ttu-id="94feb-550">Приложение группы ответа дает агентам возможность получать доступ к полезной информации в режиме реального времени с помощью встроенной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="94feb-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="94feb-551">К сожалению, графическое представление этих данных недоступно вне приложения.</span><span class="sxs-lookup"><span data-stu-id="94feb-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="94feb-552">Средство Live Resource Kit Agent Agent решает эту проблему, предоставляя простой и графический способ доступа к этой информации, дополненный в режиме реального времени Microsoft Lync 2013 Communications Software Information, например присутствие других агентов.</span><span class="sxs-lookup"><span data-stu-id="94feb-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-553">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-553">Description</span></span>

<span data-ttu-id="94feb-554">Агент группы ответа Live — это приложение Windows, которое предоставляет функции входа и выхода, а также некоторые сведения в режиме реального времени (например, сведения о членстве в группах и текущем количестве звонков) для агентов группы ответа.</span><span class="sxs-lookup"><span data-stu-id="94feb-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="94feb-555">Она должна быть расширенной версией страницы группы агентов (доступна в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-556">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-556">Purpose</span></span>

<span data-ttu-id="94feb-557">Приложение группы ответа ставит в очередь входящие вызовы, а затем направляет их в группы агентов.</span><span class="sxs-lookup"><span data-stu-id="94feb-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="94feb-558">Для принятия обоснованных решений о вызовах служб агенты могут получать доступ к сведениям о группах агентов в режиме реального времени, например о том, какие другие агенты доступны и сколько вызовов ожидают в каждой очереди.</span><span class="sxs-lookup"><span data-stu-id="94feb-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="94feb-559">Эта информация, изначально доступная только через службу группы ответа, становится доступной интуитивно понятным образом агентом группы ответа Live.</span><span class="sxs-lookup"><span data-stu-id="94feb-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="94feb-560">Возможности</span><span class="sxs-lookup"><span data-stu-id="94feb-560">Features</span></span>

<span data-ttu-id="94feb-561">Средство Live Agent Agent построено на основе службы группы ответа и пакета SDK для Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="94feb-562">Он предоставляет агентам группы ответа сведения и возможности, доступные в службе группы ответа (например, сведения о членстве в группах, присутствии других агентов и количестве ожидающих вызовов).</span><span class="sxs-lookup"><span data-stu-id="94feb-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="94feb-563">На приведенном ниже рисунке показан основной интерфейс агента группы ответа Live.</span><span class="sxs-lookup"><span data-stu-id="94feb-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="94feb-564">![Средство Live Agent Agent (агент группы ответа).](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Средство Live Agent Agent (агент группы ответа).")</span><span class="sxs-lookup"><span data-stu-id="94feb-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="94feb-565">Для агентов в действующем агенте группы ответа доступны следующие три основные функции:</span><span class="sxs-lookup"><span data-stu-id="94feb-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="94feb-566">**Вход и выход:** В отличие от страницы "группы агентов" (доступного из Lync 2013), агент группы ответа Live позволяет только агентам выполнять вход или выход из всех групп агентов одновременно.</span><span class="sxs-lookup"><span data-stu-id="94feb-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="94feb-567">Это приложение предоставляет три быстрых способа для входа и выхода:</span><span class="sxs-lookup"><span data-stu-id="94feb-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="94feb-568">Нажмите кнопки Вход/выход (зеленая и красная) в приложении.</span><span class="sxs-lookup"><span data-stu-id="94feb-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="94feb-569">Щелкните правой кнопкой мыши значок System табло и выберите команду войти или выйти.</span><span class="sxs-lookup"><span data-stu-id="94feb-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="94feb-570">Использование настраиваемых сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="94feb-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="94feb-571">**Членство в группе:** Если выбрана группа агентов, Live Agent Agent (агент группы ответа) отображает список агентов в этой группе на правой панели.</span><span class="sxs-lookup"><span data-stu-id="94feb-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="94feb-572">Если Lync 2013 запущен на том же компьютере, что и это приложение, сведения о присутствии и карточка контакта отображаются в поле агент группы ответа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="94feb-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="94feb-573">Агенты могут отправлять мгновенные сообщения или вызывать другие агенты непосредственно из него.</span><span class="sxs-lookup"><span data-stu-id="94feb-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="94feb-574">**Статистика в режиме реального времени:** Агент группы ответа Live предоставляет статистику в режиме реального времени для всех групп агентов.</span><span class="sxs-lookup"><span data-stu-id="94feb-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="94feb-575">Частота обновления составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="94feb-575">The update frequency is one minute.</span></span> <span data-ttu-id="94feb-576">Когда группа ответа отвечает на вызов, рядом с именем группы добавляется визуальный индикатор с текущим количеством вызовов в очереди.</span><span class="sxs-lookup"><span data-stu-id="94feb-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="94feb-577">При приостановке указателя над группой также отображается самое большое время ожидания.</span><span class="sxs-lookup"><span data-stu-id="94feb-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-578">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-578">Requirements</span></span>

<span data-ttu-id="94feb-579">Для работы агента группы ответа в Live требуется .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="94feb-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="94feb-580">Кроме того, чтобы воспользоваться преимуществами функций присутствия и карточки контакта, Lync 2013 должен быть установлен локально (и запущен).</span><span class="sxs-lookup"><span data-stu-id="94feb-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="94feb-581">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="94feb-581">Configuration</span></span>

<span data-ttu-id="94feb-582">Активный агент группы ответа можно изменить на индивидуальные настройки с помощью диалогового окна "Параметры" в приложении.</span><span class="sxs-lookup"><span data-stu-id="94feb-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="94feb-583">Кроме того, администратор может определить адрес узла по умолчанию, отредактировав непосредственно свойство Дефаулсостаддресс файла RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="94feb-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="94feb-584">На приведенном ниже рисунке показано диалоговое окно "Параметры", которое агенты могут использовать для настройки адреса узла и сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="94feb-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="94feb-585">Для доступа к этому диалоговому окну нажмите кнопку Параметры в правом верхнем углу основного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="94feb-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="94feb-586">![Диалоговое окно "Параметры агента группы ответа".](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Диалоговое окно "Параметры агента группы ответа".")</span><span class="sxs-lookup"><span data-stu-id="94feb-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="94feb-587">В динамической конфигурации агента группы ответа можно настроить следующие три различных параметра:</span><span class="sxs-lookup"><span data-stu-id="94feb-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="94feb-588">Адрес узла: обычно это полное доменное имя веб-пула, которое принадлежит домашнему пулу агента.</span><span class="sxs-lookup"><span data-stu-id="94feb-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="94feb-589">Точный адрес службы группы ответа автоматически создается на заднем плане от этих сведений (путем добавления правильного пути после размещения узла).</span><span class="sxs-lookup"><span data-stu-id="94feb-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="94feb-590">Сочетания клавиш: можно изменить точные сочетания клавиш для входа и выхода.</span><span class="sxs-lookup"><span data-stu-id="94feb-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="94feb-591">Единственное ограничение состоит в том, что оба сочетания клавиш должны содержать клавишу Windows Logo (помимо по крайней мере еще одного ключа).</span><span class="sxs-lookup"><span data-stu-id="94feb-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="94feb-592">Начните с Windows: приложение может быть настроено на автоматический запуск с Windows.</span><span class="sxs-lookup"><span data-stu-id="94feb-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-593">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-593">Examples</span></span>

<span data-ttu-id="94feb-594">На приведенном ниже рисунке показано, как вызвать или отправить мгновенное сообщение другому агенту, щелкнув контакт правой кнопкой мыши в правой области.</span><span class="sxs-lookup"><span data-stu-id="94feb-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="94feb-595">![Выполнение вызова или отправка мгновенного сообщения.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Выполнение вызова или отправка мгновенного сообщения.")</span><span class="sxs-lookup"><span data-stu-id="94feb-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="94feb-596">На приведенном ниже рисунке показано, как Live агент группы ответа отображает текущее число вызовов в очереди и самое большое время ожидания для всех входящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="94feb-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="94feb-597">![Просмотр сведений об очереди.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Просмотр сведений об очереди.")</span><span class="sxs-lookup"><span data-stu-id="94feb-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-598">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-598">Summary</span></span>

<span data-ttu-id="94feb-599">При быстром входе и выходе, членстве в группах и базовой статистике в режиме реального времени используются интересные функции агента группы ответа, которые доступны только вне приложения из службы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="94feb-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="94feb-600">С помощью средства Live Resource Kit Agent Agent администраторы Lync могут предоставлять свои агенты с помощью приложения Windows, позволяющего выполнять задачи быстрее и графически.</span><span class="sxs-lookup"><span data-stu-id="94feb-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="94feb-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="94feb-601">SEFAUtil</span></span>

<span data-ttu-id="94feb-602">SEFAUtil (дополнительный добавочный номер активации) — это средство командной строки, которое позволяет администраторам и агентам связи Microsoft Lync Server 2013, а также агентам групп поддержки настраивать для делегирования звонков, переадресации вызовов, одновременных звонков, параметров групповых звонков и группового ответа на звонки от имени пользователя Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="94feb-603">Кроме того, с помощью этого средства администраторы могут запрашивать параметры маршрутизации вызовов, опубликованные для определенного пользователя. Средство SEFAUtil позволяет администратору включать, отключать и изменять переадресацию вызовов или одновременно звонить от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="94feb-604">Администратор может указать целевой объект (в виде URI SIP) или использовать целевой объект, уже опубликованный пользователем.</span><span class="sxs-lookup"><span data-stu-id="94feb-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="94feb-605">Кроме того, это средство позволяет администраторам добавлять и удалять делегатов или участников группы звонков группы от имени пользователя. Это средство основано на Microsoft Unified Communications Managed API (UCMA) 3,0 и требует, чтобы администраторы создавали доверенное приложение в центральном хранилище управления для SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="94feb-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="94feb-606">SEFAUtil (дополнительный добавочный номер функции расширения) позволяет администраторам Lync Server 2013 и агентам службы поддержки настраивать делегирование звонков, переадресацию вызовов, одновременные звонки, параметры групповой связи и групповые звонки от имени пользователя Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="94feb-607">Это средство также позволяет администраторам запрашивать параметры маршрутизации вызовов, опубликованные для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-608">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-608">Description</span></span>

<span data-ttu-id="94feb-609">Текущей версией SEFAUtil является только средство командной строки; нет поддерживающего графического пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="94feb-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="94feb-610">Это средство основано на Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="94feb-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="94feb-611">Функции этого средства позволяют администраторам и агентам службы поддержки выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="94feb-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="94feb-612">Просмотр всех параметров маршрутизации вызовов для пользователя (включая переадресацию звонков, делегирование, Одновременный звонок, вызов по команде и групповые звонки)</span><span class="sxs-lookup"><span data-stu-id="94feb-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="94feb-613">Включение, отключение и изменение параметра переадресации вызовов (включая таймер "назначение" и "нет ответа")</span><span class="sxs-lookup"><span data-stu-id="94feb-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="94feb-614">Включение, отключение и изменение немедленных конфигураций пересылки вызовов</span><span class="sxs-lookup"><span data-stu-id="94feb-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="94feb-615">Включение, отключение и изменение параметров делегирования</span><span class="sxs-lookup"><span data-stu-id="94feb-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="94feb-616">Включение, отключение и изменение параметров группы звонков в группе</span><span class="sxs-lookup"><span data-stu-id="94feb-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94feb-617">Новое в Lync Server 2013 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="94feb-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="94feb-618">Включение, отключение и изменение параметров одновременных звонков (включая назначение)</span><span class="sxs-lookup"><span data-stu-id="94feb-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94feb-619">Новое в Lync Server 2013 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="94feb-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="94feb-620">Включение, отключение и изменение параметров ответа на групповые звонки</span><span class="sxs-lookup"><span data-stu-id="94feb-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="94feb-621">Новое в Lync Server 2013 SEFAUtil Tool</span><span class="sxs-lookup"><span data-stu-id="94feb-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="94feb-622">Это средство имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="94feb-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="94feb-623">Поддерживается только для пользователей, размещенных в пуле Lync Server</span><span class="sxs-lookup"><span data-stu-id="94feb-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="94feb-624">Массовое изменение параметров маршрутизации звонков для нескольких пользователей не поддерживается</span><span class="sxs-lookup"><span data-stu-id="94feb-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-625">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-625">Output</span></span>

<span data-ttu-id="94feb-626">Текущая версия этого средства предоставляет выходные данные только в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="94feb-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="94feb-627">Дополнительные сведения см. в разделе "примеры" Далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="94feb-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-628">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-628">Purpose</span></span>

<span data-ttu-id="94feb-629">Ниже приведены некоторые ключевые сценарии, в которых можно использовать это средство:</span><span class="sxs-lookup"><span data-stu-id="94feb-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="94feb-630">Боб является руководителем и перемещен на телефонию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="94feb-631">У него есть делегирование в существующей системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="94feb-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="94feb-632">В рамках перемещения в Lync администратор может настроить маршрутизацию Боба в соответствии с существующей конфигурацией делегирования.</span><span class="sxs-lookup"><span data-stu-id="94feb-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="94feb-633">Алиса движется и осознает, что она ожидает важный звонок от одного из клиентов.</span><span class="sxs-lookup"><span data-stu-id="94feb-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="94feb-634">Однако она находится в отеле и не имеет доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="94feb-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="94feb-635">Она звонит в службу поддержки и запрашивает у нее все звонки, выполненные на свой номер рабочего телефона.</span><span class="sxs-lookup"><span data-stu-id="94feb-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="94feb-636">Сотрудники службы поддержки могут выполнять настройку от его имени.</span><span class="sxs-lookup"><span data-stu-id="94feb-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="94feb-637">Звонки Джо на свой рабочий номер будут передаются в мобильную голосовую почту, когда он работает; Тем не менее, некоторые из них работают правильно в других расположениях.</span><span class="sxs-lookup"><span data-stu-id="94feb-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="94feb-638">Специалист по технической поддержки может просматривать конфигурацию маршрутизации Джо и обнаруживать, что у Ивана есть одновременные звонки, настроенные на мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="94feb-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="94feb-639">Специалист запрашивает Иван о покрытии мобильного качества на своем офисе и может определить, что одновременное правило вызывает отдачу голосовых голосовых вызовов Джо на мобильную голосовую почту, если ее работа неудовлетворительна.</span><span class="sxs-lookup"><span data-stu-id="94feb-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="94feb-640">Майк — это новый сотрудник в компании Contoso, который присоединяется к новой команде, для которой все участники настроены для работы с командой, при включении Microsoft Lync администратор может настроить параметры группы звонков группы для включения всех своих новых участников группы, а администратор добавляет в качестве участника группы звонков "Mike" участника группы для каждого участника в своей команде.</span><span class="sxs-lookup"><span data-stu-id="94feb-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="94feb-641">Обслуживание клиентов в отделе кадров компании Contoso заключается в предоставлении личной службы для всех абонентов с момента первого звонка.</span><span class="sxs-lookup"><span data-stu-id="94feb-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="94feb-642">С учетом того, что все участники отдела располагаются близко друг к другу, и все телефоны в то же время с помощью командного вызова очень нарушают эту группу.</span><span class="sxs-lookup"><span data-stu-id="94feb-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="94feb-643">Чтобы обеспечить лучшую службу, не нарушая участников группы, администратор Lync использует функцию отправки групповых вызовов.</span><span class="sxs-lookup"><span data-stu-id="94feb-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="94feb-644">Администратор добавляет всех участников отдела в группу раскладки и передает их в отделный номер группы раскладки.</span><span class="sxs-lookup"><span data-stu-id="94feb-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="94feb-645">Когда Samantha отсутствует на рабочем месте, Джо заметит его телефонный звонок и выберет на себя ответ на звонок со своего рабочего места.</span><span class="sxs-lookup"><span data-stu-id="94feb-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-646">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-646">Requirements</span></span>

<span data-ttu-id="94feb-647">Средство SEFAUtil можно запустить только на компьютере, который является частью пула доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="94feb-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="94feb-648">На этом компьютере должен быть установлен UCMA 3,0.</span><span class="sxs-lookup"><span data-stu-id="94feb-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="94feb-649">Для запуска средства необходимо создать в этом пуле новое доверенное приложение с ИДЕНТИФИКАТОРом приложения SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="94feb-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="94feb-650">**Создание нового доверенного приложения для средства SEFAUtil**</span><span class="sxs-lookup"><span data-stu-id="94feb-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="94feb-651">Средство SEFAUTil можно запускать только на компьютере, входящем в пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="94feb-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="94feb-652">При необходимости Добавление пула в качестве нового доверенного пула приложений можно выполнить с помощью командной консоли Lync Server с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="94feb-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94feb-653">UCMA 3,0 должен быть установлен на компьютере, который будет использоваться для запуска средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="94feb-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="94feb-654">Доверенное приложение должно быть определено в топологии для средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="94feb-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="94feb-655">Чтобы определить SEFAUtil как новое доверенное приложение, используйте командную консоль Lync Server и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="94feb-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94feb-656">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="94feb-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="94feb-657">Необходимо включить изменения топологии.</span><span class="sxs-lookup"><span data-stu-id="94feb-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="94feb-658">Включение изменений топологии можно выполнить с помощью командной консоли Lync Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="94feb-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="94feb-659">При необходимости установите средства набора ресурсов Lync Server 2013 на сервер, который будет использоваться для запуска средства SEFAUtil (сервер должен быть частью пула доверенных приложений).</span><span class="sxs-lookup"><span data-stu-id="94feb-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="94feb-660">Убедитесь, что SEFAUtil работает правильно.</span><span class="sxs-lookup"><span data-stu-id="94feb-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="94feb-661">Для этого запустите средство из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="94feb-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="94feb-662">По умолчанию оно размещается в: "... \\ Файлы программ \\ Microsoft Lync Server 2013 \\ reskit ".</span><span class="sxs-lookup"><span data-stu-id="94feb-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="94feb-663">Чтобы отобразить параметры переадресации звонков для пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="94feb-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="94feb-664">Должны отобразиться параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="94feb-665">Ответ на групповой вызов</span><span class="sxs-lookup"><span data-stu-id="94feb-665">Group Call Pickup</span></span>

<span data-ttu-id="94feb-666">Для того чтобы возможность полностью активировать возможность для группового ответа на вызовы, требуется дополнительная настройка в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="94feb-667">Перед назначением групп раскладки пользователям обратитесь к документации по продукту, чтобы получить сведения о планировании и развертывании этой возможности.</span><span class="sxs-lookup"><span data-stu-id="94feb-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-668">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="94feb-669">Отображение текущих параметров обработки звонков</span><span class="sxs-lookup"><span data-stu-id="94feb-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="94feb-670">Следующая команда отображает обработку вызовов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-671">В этом примере параметр <STRONG>/Server</STRONG> используется для указания сервера Lync Server, к которому нужно подключиться.</span><span class="sxs-lookup"><span data-stu-id="94feb-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="94feb-672">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="94feb-673">Установка назначения "переадресация вызовов/нет ответа"</span><span class="sxs-lookup"><span data-stu-id="94feb-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="94feb-674">В этом примере задается назначение ответа "перенаправление вызова", "нет ответа" и "Задержка звонка".</span><span class="sxs-lookup"><span data-stu-id="94feb-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="94feb-675">В этом случае параметр/Server не предоставляется; SEFAUtil пытается выполнить Автообнаружение сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94feb-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="94feb-676">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="94feb-677">Немедленное включение переадресации вызовов</span><span class="sxs-lookup"><span data-stu-id="94feb-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="94feb-678">В этом примере сразу же включается переадресация звонков для другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="94feb-679">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="94feb-680">Немедленное отключение переадресации вызовов</span><span class="sxs-lookup"><span data-stu-id="94feb-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="94feb-681">В этом примере немедленно отключается переадресация вызовов.</span><span class="sxs-lookup"><span data-stu-id="94feb-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="94feb-682">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="94feb-683">Добавление пользователя в качестве делегата и настройка одновременных звонков делегатов</span><span class="sxs-lookup"><span data-stu-id="94feb-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="94feb-684">В этом примере пользователь добавляется в качестве делегата и настраивает Одновременный звонок делегатов.</span><span class="sxs-lookup"><span data-stu-id="94feb-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="94feb-685">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="94feb-686">Изменение правила одновременных звонков делегатов</span><span class="sxs-lookup"><span data-stu-id="94feb-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="94feb-687">В этом примере изменяется правило одновременных звонков, которое было задано в предыдущем примере, в правило задержанных звонков.</span><span class="sxs-lookup"><span data-stu-id="94feb-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="94feb-688">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="94feb-689">Удаление делегата</span><span class="sxs-lookup"><span data-stu-id="94feb-689">Remove the Delegate</span></span>

<span data-ttu-id="94feb-690">В этом примере удаляется делегат.</span><span class="sxs-lookup"><span data-stu-id="94feb-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-691">При удалении последнего делегата делегат автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="94feb-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="94feb-692">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="94feb-693">Добавление делегата и настройка правила Call-Forward для делегатов</span><span class="sxs-lookup"><span data-stu-id="94feb-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="94feb-694">В этом примере добавляется делегат и настраивается правило перенаправления звонка на делегаты.</span><span class="sxs-lookup"><span data-stu-id="94feb-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="94feb-695">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="94feb-696">Включение одновременных звонков и задание номера назначения</span><span class="sxs-lookup"><span data-stu-id="94feb-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="94feb-697">В этом примере включается Одновременный звонок и задается номер назначения для одновременного звонка.</span><span class="sxs-lookup"><span data-stu-id="94feb-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-698">Чтобы изменить номер назначения одновременного звонка для пользователя, для которого уже включен Одновременный звонок, оставьте команду с параметром/енаблесимулринг, в противном случае целевой номер не изменится.</span><span class="sxs-lookup"><span data-stu-id="94feb-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="94feb-699">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="94feb-700">Отключение одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="94feb-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="94feb-701">В этом примере отключается Одновременный звонок.</span><span class="sxs-lookup"><span data-stu-id="94feb-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="94feb-702">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="94feb-703">Добавление члена группы для Team-Call и настройка одновременных звонков в группу Team-Call участников</span><span class="sxs-lookup"><span data-stu-id="94feb-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="94feb-704">В этом примере участник группы добавляется в группу звонков пользователя и включает одновременный Звонок группе звонков группы.</span><span class="sxs-lookup"><span data-stu-id="94feb-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-705">При добавлении участника в группу звонков для пользователя автоматически переключается Одновременный звонок сеттигс пользователей на выполнение его группу звонков в группу.</span><span class="sxs-lookup"><span data-stu-id="94feb-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="94feb-706">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="94feb-707">Удаление участника из группы Team-Call</span><span class="sxs-lookup"><span data-stu-id="94feb-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="94feb-708">В этом примере удаляется участник команды группы звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-709">Если удаляемый член является единственным участником группы звонков группы, одновременно звонить группе звонков группы будет автоматически отключено.</span><span class="sxs-lookup"><span data-stu-id="94feb-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="94feb-710">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="94feb-711">Установка отложенного звонка в группу Team-Call</span><span class="sxs-lookup"><span data-stu-id="94feb-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="94feb-712">В этом примере показано, как изменить параметр времени в группе звонков группы звонков.</span><span class="sxs-lookup"><span data-stu-id="94feb-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="94feb-713">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="94feb-714">Включение Team-Call</span><span class="sxs-lookup"><span data-stu-id="94feb-714">Enable Team-Call</span></span>

<span data-ttu-id="94feb-715">В этом примере включается групповой звонок для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-716">Если группа вызовов пользователя не имеет участников, вызов по команде не будет включен.</span><span class="sxs-lookup"><span data-stu-id="94feb-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="94feb-717">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="94feb-718">Отключение Team-Call</span><span class="sxs-lookup"><span data-stu-id="94feb-718">Disable Team-Call</span></span>

<span data-ttu-id="94feb-719">В этом примере отключается вызов по команде для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="94feb-720">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="94feb-721">Включение групповой отправки звонков и назначение группы раскладки пользователю</span><span class="sxs-lookup"><span data-stu-id="94feb-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="94feb-722">В этом примере группа раскладки назначается пользователю и включается запрос группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="94feb-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="94feb-723">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="94feb-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="94feb-724">Отключение отправки группового звонка</span><span class="sxs-lookup"><span data-stu-id="94feb-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="94feb-725">В этом примере отключается отправка группового звонка для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-726">При отключении групповой отправки звонков для пользователя номер группы, назначенный пользователю, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="94feb-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="94feb-727">Если вы попытаетесь повторно включить запрос групп для этого пользователя, необходимо повторно назначить номер группы с помощью параметра/енаблеграуппиккуп.</span><span class="sxs-lookup"><span data-stu-id="94feb-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="94feb-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="94feb-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-729">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-729">Description</span></span>

<span data-ttu-id="94feb-730">SYSPrep.ps1 — это сценарий Windows PowerShell, который будет устанавливать следующие необходимые компоненты Lync Server 2013 на компьютер с операционной системой Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="94feb-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="94feb-731">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="94feb-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="94feb-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="94feb-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="94feb-733">Windows PowerShell версии 3,0</span><span class="sxs-lookup"><span data-stu-id="94feb-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="94feb-734">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="94feb-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="94feb-735">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="94feb-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="94feb-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="94feb-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="94feb-737">Основные файлы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94feb-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="94feb-738">Имя скрипта аналогично средству подготовки системы для операционных систем Microsoft Windows, но они отличаются.</span><span class="sxs-lookup"><span data-stu-id="94feb-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="94feb-739">Этот сценарий установит только необходимые компоненты для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="94feb-740">После установки необходимых компонентов средство SYSPrep можно использовать для создания образа сервера.</span><span class="sxs-lookup"><span data-stu-id="94feb-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-741">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-741">Requirements</span></span>

<span data-ttu-id="94feb-742">Перед выполнением скрипта SYSPrep.ps1 необходимо скопировать файлы необходимых компонентов в локальную папку на компьютере с операционной системой Windows Server 2008 (например, **D: \\ Setup)**.</span><span class="sxs-lookup"><span data-stu-id="94feb-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="94feb-743">Эта папка также должна содержать копию файлов Lync Server 2013, а именно **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="94feb-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="94feb-744">Файлы необходимых компонентов можно скачать из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="94feb-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94feb-745">Необходимого</span><span class="sxs-lookup"><span data-stu-id="94feb-745">Prerequisite</span></span></th>
<th><span data-ttu-id="94feb-746">Расположение</span><span class="sxs-lookup"><span data-stu-id="94feb-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94feb-747">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="94feb-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94feb-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="94feb-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94feb-749">Windows PowerShell версии 3,0</span><span class="sxs-lookup"><span data-stu-id="94feb-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94feb-750">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="94feb-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94feb-751">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="94feb-751">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94feb-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="94feb-752">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94feb-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="94feb-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="94feb-754">Копирование с носителя Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94feb-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="94feb-755">Параметр</span><span class="sxs-lookup"><span data-stu-id="94feb-755">Parameter</span></span>

<span data-ttu-id="94feb-756">Параметр **– сетупфолдер** принимает в качестве аргумента расположение каталога необходимых файлов</span><span class="sxs-lookup"><span data-stu-id="94feb-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-757">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-757">Examples</span></span>

<span data-ttu-id="94feb-758">Чтобы запустить скрипт SYSPrep.ps1 и установить необходимые компоненты Lync Server 2013, выполните следующую команду из командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="94feb-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="94feb-759">Миграция объявлений неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="94feb-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="94feb-760">Средство миграции оповещений о неназначенных номерах позволяет администратору Lync перемещать конфигурацию неназначенных номеров, обслуживаемую приложением-оповещением с исходного сервера или пула Lync на целевой сервер Lync или в пул.</span><span class="sxs-lookup"><span data-stu-id="94feb-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-761">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-761">Description</span></span>

<span data-ttu-id="94feb-762">Средство миграции объявлений неназначенных номеров — это сценарий Windows PowerShell, который перемещает конфигурацию неназначенных номеров, обслуживаемую приложением-объявлением исходного сервера или пула, на другой сервер или в пул.</span><span class="sxs-lookup"><span data-stu-id="94feb-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="94feb-763">При выполнении сценарий миграции неназначенных номеров будет выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="94feb-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="94feb-764">Переместите все звуковые файлы, используемые объявлениями неназначенных номеров приложения, размещенного на исходном сервере или в хранилище файлов на целевом сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94feb-765">звуковые файлы удаляются из исходного пула после их копирования в конечный пул.</span><span class="sxs-lookup"><span data-stu-id="94feb-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="94feb-766">Переместите все объявления неназначенных номеров, настроенные для приложения для оповещений, размещенного на исходном сервере или в пуле, на целевом сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="94feb-767">Переназначение всех диапазонов неназначенных номеров, обслуживаемых приложением для извещения, размещенным на исходном сервере или в пуле, на конечный сервер или в пул.</span><span class="sxs-lookup"><span data-stu-id="94feb-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="94feb-768">После успешного выполнения сценария все диапазоны неназначенных номеров, Обслуживаемые приложением, размещенным на исходном сервере или в пуле, теперь будут обслуживаться с одинаковой конфигурацией на целевом сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="94feb-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-769">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-769">Output</span></span>

<span data-ttu-id="94feb-770">Сценарий **Move – CsAnnouncementConfiguration** указывает в окне Командная консоль Lync, откуда она выполняла успешную или неудачную операцию миграции.</span><span class="sxs-lookup"><span data-stu-id="94feb-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="94feb-771">Если выполнение операции прервано из-за любой ошибки, диапазоны неназначенных номеров, которые были успешно перемещены в назначение, останутся в месте назначения в рабочей форме, а остальные диапазоны неназначенных номеров для переноса останутся в источнике, а также в рабочей форме.</span><span class="sxs-lookup"><span data-stu-id="94feb-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="94feb-772">Чтобы полностью перенести оставшуюся часть конфигурации, повторно запустите сценарий после устранения ошибки.</span><span class="sxs-lookup"><span data-stu-id="94feb-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="94feb-773">Назначение</span><span class="sxs-lookup"><span data-stu-id="94feb-773">Purpose</span></span>

<span data-ttu-id="94feb-774">Сценарий переноса оповещений о неназначенных номерах можно использовать в следующих трех сценариях:</span><span class="sxs-lookup"><span data-stu-id="94feb-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="94feb-775">**Перенос параметров конфигурации в новую версию Lync Server:** Компания Contoso находится в процессе миграции на Lync Server 2013 и в рамках процесса миграции администратору Lync Server требуется переместить конфигурацию неназначенных номеров, обслуживаемую приложением-оповещением, из развертывания Lync Server 2010 в новое развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="94feb-776">Для перемещения параметров конфигурации администратор Lync Server использует средство миграции объявлений о неназначенных номерах.</span><span class="sxs-lookup"><span data-stu-id="94feb-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="94feb-777">**Откат развертывания с Lync server 2013 на Lync server 2010:** Из-за непредвиденных факторов компания Contoso должна откатить миграцию на новое развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="94feb-778">Чтобы свести к минимуму перерывы в работе службы, администратор Lync Server использует средство миграции объявлений о неназначенных номерах для отката конфигурации из развертывания Lync Server 2013 к развертыванию Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="94feb-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="94feb-779">**Перемещение данных между развертываниями Lync:** Компания Contoso находится в процессе замены всех серверов в одном пуле на новые серверы.</span><span class="sxs-lookup"><span data-stu-id="94feb-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="94feb-780">Их стратегия заключается в развертывании нового пула Lync Server 2013, перенос всех данных из старого в новый пул, а затем использование старого пула.</span><span class="sxs-lookup"><span data-stu-id="94feb-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="94feb-781">После развертывания нового пула средство миграции объявлений неназначенных номеров используется для перемещения конфигурации из старого пула в новый.</span><span class="sxs-lookup"><span data-stu-id="94feb-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-782">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-782">Requirements</span></span>

<span data-ttu-id="94feb-783">Ниже приведены основные требования, необходимые для успешного запуска средства.</span><span class="sxs-lookup"><span data-stu-id="94feb-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="94feb-784">Скрипт необходимо запускать на компьютере с установленной консолью управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94feb-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="94feb-785">Приложение объявления должно быть успешно развернуто на исходном и целевом серверах Lync или пулах.</span><span class="sxs-lookup"><span data-stu-id="94feb-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="94feb-786">Move-CsAnnouncementConfiguration Скрипт</span><span class="sxs-lookup"><span data-stu-id="94feb-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="94feb-787">Для сценария Move-CsAnnouncementConfiguration необходимы два параметра, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="94feb-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="94feb-788">![Параметры Move – CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration параметры.")</span><span class="sxs-lookup"><span data-stu-id="94feb-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-789">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="94feb-790">Перемещение конфигурации объявлений неназначенных номеров из пула Lync Server 2010 в пул Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94feb-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="94feb-791">В этом примере объявления неназначенных номеров перемещаются из исходного пула (Lync Server 2010) в целевой пул (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="94feb-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="94feb-792">Перемещение конфигурации объявлений неназначенных номеров из пула Lync Server 2013 в пул Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="94feb-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="94feb-793">В этом примере объявления неназначенных номеров перемещаются из исходного пула (Lync Server 2013) в целевой пул (Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="94feb-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="94feb-794">Данные Web CONF</span><span class="sxs-lookup"><span data-stu-id="94feb-794">Web Conf Data</span></span>

<span data-ttu-id="94feb-795">Средство Web CONF Data позволяет администратору Lync Server 2013 Communications программного обеспечения контролировать данные, связанные с веб-конференциями организатора.</span><span class="sxs-lookup"><span data-stu-id="94feb-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="94feb-796">Сценарии включают возможность удалять данные о собрании определенного пользователя на основе условий штампа времени.</span><span class="sxs-lookup"><span data-stu-id="94feb-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="94feb-797">Описание</span><span class="sxs-lookup"><span data-stu-id="94feb-797">Description</span></span>

<span data-ttu-id="94feb-798">Это средство позволяет администратору выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="94feb-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="94feb-799">Поиск всех данных веб-конференций, связанных с одним пользователем.</span><span class="sxs-lookup"><span data-stu-id="94feb-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="94feb-800">Удалить все данные веб-конференций, связанные с отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="94feb-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="94feb-801">Удалить все данные веб-конференций, связанные с одним пользователем старше определенной даты.</span><span class="sxs-lookup"><span data-stu-id="94feb-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="94feb-802">Переместить все данные веб-конференций, связанные с отдельным пользователем, когда пользователь перемещается из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="94feb-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94feb-803">Средства набора ресурсов для Lync Server 2010 поддерживают перемещение всех данных веб-конференций, связанных с одним пользователем, когда пользователь перемещается из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="94feb-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="94feb-804">Эта функция теперь нерекомендуема для этого средства в пользу параметра <STRONG>мовеконференцедата</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="94feb-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="94feb-805">Для получения дополнительных сведений об этом параметре обратитесь к командлету <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move – CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="94feb-805">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="94feb-806">Средство удаляет данные собраний только для неактивных собраний.</span><span class="sxs-lookup"><span data-stu-id="94feb-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="94feb-807">Невозможно удалить активные собрания (или собрания в сеансах).</span><span class="sxs-lookup"><span data-stu-id="94feb-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="94feb-808">Это средство необходимо запускать на компьютере, который находится в том же пуле, что и целевой пользователь.</span><span class="sxs-lookup"><span data-stu-id="94feb-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="94feb-809">Пользователи, чьи данные контента собраний управляются этим средством, должны находиться в том же пуле пользователей.</span><span class="sxs-lookup"><span data-stu-id="94feb-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="94feb-810">Output</span><span class="sxs-lookup"><span data-stu-id="94feb-810">Output</span></span>

<span data-ttu-id="94feb-811">Это средство выводит результаты каждой из операций:</span><span class="sxs-lookup"><span data-stu-id="94feb-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="94feb-812">Если выполняется запрос, средство выводит список всех неактивных папок с данными собраний, в которых этот пользователь является организатором.</span><span class="sxs-lookup"><span data-stu-id="94feb-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="94feb-813">Если выполняется удаление, средство выводит список всех папок с данными собраний, чьи данные будут удалены.</span><span class="sxs-lookup"><span data-stu-id="94feb-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="94feb-814">Требования</span><span class="sxs-lookup"><span data-stu-id="94feb-814">Requirements</span></span>

<span data-ttu-id="94feb-815">Средство должно быть запущено в том же пуле, в котором в данный момент размещен Организатор.</span><span class="sxs-lookup"><span data-stu-id="94feb-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="94feb-816">Средство необходимо запускать с правами администратора с доступом к хранилищу файлов контента.</span><span class="sxs-lookup"><span data-stu-id="94feb-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="94feb-817">Примеры</span><span class="sxs-lookup"><span data-stu-id="94feb-817">Examples</span></span>

<span data-ttu-id="94feb-818">В следующей таблице описываются параметры, некоторые из которых используются в примерах.</span><span class="sxs-lookup"><span data-stu-id="94feb-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="94feb-819">![Параметры Web CONF Data Tool.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Параметры Web CONF Data Tool.")</span><span class="sxs-lookup"><span data-stu-id="94feb-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="94feb-820">В предыдущем примере показано, как работает команда запроса.</span><span class="sxs-lookup"><span data-stu-id="94feb-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="94feb-821">Результатом такой команды будет список всех папок контента собраний, которые будут затронуты этим средством.</span><span class="sxs-lookup"><span data-stu-id="94feb-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="94feb-822">Предыдущий пример команды DELETE.</span><span class="sxs-lookup"><span data-stu-id="94feb-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="94feb-823">Команда Delete удалит все неактивные папки собраний от этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="94feb-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="94feb-824">Аннотация</span><span class="sxs-lookup"><span data-stu-id="94feb-824">Summary</span></span>

<span data-ttu-id="94feb-825">Это средство может быть ценным ресурсом для администраторов, которым необходим более точный контроль над данными для собраний по конференциям.</span><span class="sxs-lookup"><span data-stu-id="94feb-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
