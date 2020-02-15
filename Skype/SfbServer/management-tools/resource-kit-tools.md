---
title: Документация по средствам набора ресурсов Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: В этом разделе описываются средства в наборе ресурсов Skype для бизнеса Server 2015, в том числе назначение каждого средства, а также приводятся примеры их использования. Пакет ресурсов Skype для бизнеса Server 2015 позволяет упростить выполнение повседневных задач для ИТ-администраторов, которые развертывают Skype для бизнеса Server 2015 и управляют им. Например, с помощью средства Web CONF Data можно легко управлять данными, отправляемыми пользователями во время собрания по сети. Средство SEFAUtil можно использовать для настройки переадресации вызовов делегатов и ответа для пользователей. Мы рекомендуем ИТ-администраторам использовать эти средства для более эффективного управления Skype для бизнеса Server 2015.
ms.openlocfilehash: ab43d8e951308fab5a4aefc25d9dad2804ea5d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005994"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="42f64-107">Документация по средствам набора ресурсов Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="42f64-108">В этом разделе описываются средства в наборе ресурсов Skype для бизнеса Server 2015, в том числе назначение каждого средства, а также приводятся примеры их использования.</span><span class="sxs-lookup"><span data-stu-id="42f64-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="42f64-109">Пакет ресурсов Skype для бизнеса Server 2015 позволяет упростить выполнение повседневных задач для ИТ-администраторов, которые развертывают Skype для бизнеса Server 2015 и управляют им.</span><span class="sxs-lookup"><span data-stu-id="42f64-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="42f64-110">Например, с помощью средства **Web CONF Data** можно легко управлять данными, отправляемыми пользователями во время собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="42f64-111">Средство **SEFAUtil** можно использовать для настройки переадресации вызовов делегатов и ответа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="42f64-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="42f64-112">Мы рекомендуем ИТ-администраторам использовать эти средства для более эффективного управления Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="42f64-113">Установка средств набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="42f64-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="42f64-114">Чтобы установить пакет ресурсов Skype для бизнеса Server 2015, скачайте [OCSReskit. msi](https://www.microsoft.com/download/details.aspx?id=52631) из центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="42f64-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="42f64-115">Запустите **OCSResKit. msi** , чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="42f64-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="42f64-116">MSI устанавливает все средства, указанные в следующем каталоге: **% Program Филес%\скипе for Business Server 2015 \ ResKit**.</span><span class="sxs-lookup"><span data-stu-id="42f64-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="42f64-117">В этой папке есть инструменты, которые представляют собой автономные исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="42f64-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="42f64-118">Средства, у которых также есть вспомогательные файлы, находятся в своих вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="42f64-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="42f64-119">Поддерживаемые среды</span><span class="sxs-lookup"><span data-stu-id="42f64-119">Supported Environments</span></span>

<span data-ttu-id="42f64-120">Пакет ресурсов Skype для бизнеса Server 2015 должен быть установлен на сервере, соответствующем спецификациям, необходимым для Skype для бизнеса Server 2015, обычно он используется для запуска Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="42f64-121">Общие сведения о средствах набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="42f64-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="42f64-122">Ниже приведен список средств, предоставленных в наборе ресурсов Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="42f64-123">Описание каждого средства, включая требования и пример использования, описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="42f64-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="42f64-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="42f64-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="42f64-125">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="42f64-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="42f64-126">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="42f64-127">Вызов Parkometer</span><span class="sxs-lookup"><span data-stu-id="42f64-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="42f64-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="42f64-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="42f64-129">Импорт данных службы хранилища</span><span class="sxs-lookup"><span data-stu-id="42f64-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="42f64-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="42f64-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="42f64-131">Консоль поиска пользователей</span><span class="sxs-lookup"><span data-stu-id="42f64-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="42f64-132">мстурнпинг</span><span class="sxs-lookup"><span data-stu-id="42f64-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="42f64-133">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="42f64-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="42f64-134">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="42f64-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="42f64-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="42f64-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="42f64-136">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="42f64-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="42f64-137">Миграция объявлений неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="42f64-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="42f64-138">Данные Web CONF</span><span class="sxs-lookup"><span data-stu-id="42f64-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="42f64-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="42f64-139">ABSConfig</span></span>
<span data-ttu-id="42f64-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="42f64-141">Средство настройки службы адресной книги (ABSConfig) — это средство администрирования, которое помогает администраторам настраивать конфигурацию службы адресной книги в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="42f64-142">Это средство также позволяет администраторам Skype для бизнеса Server 2015 восстановить параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="42f64-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-143">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-143">Description</span></span>

<span data-ttu-id="42f64-144">ABSConfig — это приложение графического пользовательского интерфейса, которое позволяет администраторам настраивать атрибуты доменных служб Active Directory, связанные со службой адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42f64-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="42f64-145">Ниже приведены основные сценарии для этого средства.</span><span class="sxs-lookup"><span data-stu-id="42f64-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="42f64-146">Чтобы разрешить администраторам сопоставлять атрибуты в доменных службах Active Directory с атрибутами Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="42f64-147">Чтобы разрешить администраторам указывать атрибут доменных служб Active Directory, который необходимо включить или исключить в файлах службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42f64-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="42f64-148">, Чтобы разрешить администраторам восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="42f64-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="42f64-149">Средство ABSConfig можно запустить с помощью файла ABSConfig. exe.</span><span class="sxs-lookup"><span data-stu-id="42f64-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="42f64-150">Средство откроется на вкладке **Настройка атрибутов** . В этой таблице представлены параметры для сопоставления атрибутов доменных служб Active Directory с полями атрибутов Skype для бизнеса Server 2015 и указания пользователей, которые следует включить или исключить в файлах службы адресной книги на основе определенных фильтров атрибутов.</span><span class="sxs-lookup"><span data-stu-id="42f64-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="42f64-151">Кроме того, можно настроить значение номера телефона, включаемого в файл адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42f64-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="42f64-152">Параметр **восстановить значения по умолчанию** позволяет администраторам восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="42f64-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="42f64-153">Повторное сопоставление атрибутов AD с другими именами полей OC будет работать только при загрузке файла адресной книги и не поддерживается веб-запросом адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42f64-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-154">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-154">Output</span></span>

<span data-ttu-id="42f64-155">ABSConfig сохраняет конфигурацию службы адресной книги в базе данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="42f64-156">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-156">Purpose</span></span>

<span data-ttu-id="42f64-157">ABSConfig предоставляет быстрый и простой способ настройки службы адресной книги Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-158">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="42f64-159">Компьютер</span><span class="sxs-lookup"><span data-stu-id="42f64-159">Computer</span></span>

<span data-ttu-id="42f64-160">ABSConfig можно запустить только с компьютера, присоединенного к домену, на котором установлен Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="42f64-161">В случае Skype для бизнеса Server 2015, Enterprise Edition это средство можно запустить на всех серверах переднего плана, на которых в процессе установки включена служба адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42f64-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="42f64-162">Сеть</span><span class="sxs-lookup"><span data-stu-id="42f64-162">Network</span></span>

<span data-ttu-id="42f64-163">Компьютер должен иметь возможность подключения к интерфейсному пулу и серверной базе данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="42f64-164">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="42f64-164">Software</span></span>

<span data-ttu-id="42f64-165">Перед запуском средства ABSConfig необходимо установить следующие компоненты программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="42f64-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="42f64-166">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="42f64-167">Пользователи</span><span class="sxs-lookup"><span data-stu-id="42f64-167">Users</span></span>

<span data-ttu-id="42f64-168">Администраторы, у которых есть разрешения, необходимые для обновления развертывания Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-169">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-169">Examples</span></span>

<span data-ttu-id="42f64-170">ABSConfig можно запустить, введя **ABSConfig. exe** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="42f64-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="42f64-171">Ниже показан пользовательский интерфейс средства ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="42f64-171">Shown below is the ABSConfig tool user interface.</span></span>

![Средство ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="42f64-173">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-173">Summary</span></span>

<span data-ttu-id="42f64-174">Средство ABSConfig предоставляет администраторам быстрые и простые в использовании средства для настройки службы адресной книги Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="42f64-175">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="42f64-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="42f64-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="42f64-177">Средство мониторинга службы политики пропускной способности позволяет администраторам просматривать список следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="42f64-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="42f64-178">Все настроенные службы политики пропускной способности Skype для бизнеса Server 2015 (проверка подлинности и ядро) в топологии</span><span class="sxs-lookup"><span data-stu-id="42f64-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="42f64-179">Подключения, которые каждая служба делает с другими службами политики пропускной способности и с пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="42f64-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="42f64-180">Все ссылки, настроенные в документе конфигурации сети и использование пропускной способности в режиме реального времени, отображаются каждой из служб политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="42f64-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="42f64-181">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-181">Description</span></span>

<span data-ttu-id="42f64-182">Монитор службы политики пропускной способности реализован в виде приложения, основанного на пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="42f64-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="42f64-183">Администраторы запускают средство, запуская Пдпмонуи. exe.</span><span class="sxs-lookup"><span data-stu-id="42f64-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="42f64-184">При запуске средства будет предпринята попытка обнаружить список служб политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="42f64-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="42f64-185">После первоначального обновления область слева от окна заполняется списком служб, сгруппированных по кластерам, к которым они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="42f64-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="42f64-186">Когда Администраторы выбирают определенную службу политики пропускной способности, в области справа отображаются сведения о конкретной службе.</span><span class="sxs-lookup"><span data-stu-id="42f64-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="42f64-187">Эта область также содержит две основные вкладки, отображающие информацию.</span><span class="sxs-lookup"><span data-stu-id="42f64-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="42f64-188">Вкладка "сведения о компьютере"</span><span class="sxs-lookup"><span data-stu-id="42f64-188">Machine Info Tab</span></span>

<span data-ttu-id="42f64-189">На вкладке **сведения о компьютере** отображаются сведения о выбранном службе политики пропускной способности, а также список и состояние всех подключений, выполняемых выбранной службой политики пропускной способности, к другим службам.</span><span class="sxs-lookup"><span data-stu-id="42f64-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="42f64-190">Вкладка "сведения о топологии"</span><span class="sxs-lookup"><span data-stu-id="42f64-190">Topology Info Tab</span></span>

<span data-ttu-id="42f64-191">На вкладке **сведения о топологии** отображается список всех ссылок, настроенных в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="42f64-192">Для каждой ссылки отображается пропускная способность звука и видео.</span><span class="sxs-lookup"><span data-stu-id="42f64-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="42f64-193">Кроме того, отображается текущая полоса пропускания (в кбит/с и в процентах от емкости).</span><span class="sxs-lookup"><span data-stu-id="42f64-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="42f64-194">Инструмент использует цветовое кодирование для выделения ссылок, которые имеют близкое к емкости значение, позволяет администраторам быстро изолировать такие ссылки.</span><span class="sxs-lookup"><span data-stu-id="42f64-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="42f64-195">Если монитор службы политики пропускной способности испытывает сбой при подключении к любой из настроенных служб политики пропускной способности, информация в разделе сведения о **компьютере** и вкладки **сведения о топологии** не будут заполнены.</span><span class="sxs-lookup"><span data-stu-id="42f64-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="42f64-196">Тем не менее, средство может подключаться изначально, но при этом теряет соединение со службой.</span><span class="sxs-lookup"><span data-stu-id="42f64-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="42f64-197">В таких случаях администраторы могут видеть устаревшую информацию.</span><span class="sxs-lookup"><span data-stu-id="42f64-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="42f64-198">На каждой из вкладок имеется штамп времени **последнего обновления** , который позволяет администраторам просматривать время последнего обновления данных для конкретной службы политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="42f64-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-199">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-199">Output</span></span>

<span data-ttu-id="42f64-200">Отсутствует вывод командной строки; выходные данные программы хранятся в основном графическом интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-201">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-201">Purpose</span></span>

<span data-ttu-id="42f64-202">Средство мониторинга службы политики пропускной способности позволяет администраторам видеть состояние каждой службы политики пропускной способности, определенной в топологии.</span><span class="sxs-lookup"><span data-stu-id="42f64-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="42f64-203">Кроме того, администраторы могут видеть использование пропускной способности в режиме реального времени для всех ссылок, определенных в документе конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-204">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-204">Requirements</span></span>

<span data-ttu-id="42f64-205">Средство мониторинга службы политики пропускной способности необходимо запускать на компьютере, входящем в топологию Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="42f64-206">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-206">Summary</span></span>

<span data-ttu-id="42f64-207">Монитор службы политики пропускной способности может быть ценным ресурсом для администраторов, чтобы они могли проверить состояние всех служб политики пропускной способности в топологии, и более важно — они могут получить использование пропускной способности в режиме реального времени для ссылок, которые определено в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="42f64-208">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="42f64-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-209"><a name="bua"> </a></span></span>

<span data-ttu-id="42f64-210">Анализатор использования полосы пропускания — это средство, которое создает отчеты о различных режимах использования полосы пропускания в конечных точках UC по каналам глобальной сети в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="42f64-211">Эти отчеты можно использовать для ознакомления с текущей моделью потребления полосы пропускания и для планирования пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="42f64-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-212">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-212">Description</span></span>

<span data-ttu-id="42f64-213">Анализатор использования полосы пропускания реализуется как приложение, основанное на пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="42f64-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="42f64-214">Это средство создает отчеты специально для использования звука в сети и помогает при планировании мощности.</span><span class="sxs-lookup"><span data-stu-id="42f64-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="42f64-215">Кроме того, он выполняет итерацию по пропускной способности, назначенной различным каналам.</span><span class="sxs-lookup"><span data-stu-id="42f64-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-216">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-216">Output</span></span>

<span data-ttu-id="42f64-217">Анализатор использования полосы пропускания предоставляет графический показатель мощности и интенсивности пропускной способности для всех каналов глобальной сети, настроенных в системе.</span><span class="sxs-lookup"><span data-stu-id="42f64-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-218">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-218">Purpose</span></span>

<span data-ttu-id="42f64-219">В любом развертывании голосовых и видеофайлов очень важно отслеживать и оценить тенденцию использования пропускной способности трафика мультимедиа в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="42f64-220">Анализатор использования полосы пропускания позволяет администратору добиться всего этого.</span><span class="sxs-lookup"><span data-stu-id="42f64-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="42f64-221">Это средство выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="42f64-221">This tool does the following:</span></span>

- <span data-ttu-id="42f64-222">Создает конкретные отчеты по использованию звука в сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="42f64-223">Способствует более эффективному планированию емкости и итерации по емкости полосы пропускания, назначенной различным связям</span><span class="sxs-lookup"><span data-stu-id="42f64-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="42f64-224">Анализатор использования полосы пропускания может создавать графические графики для отчетов о емкости и использовании полосы пропускания; они перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="42f64-225">Все связи WAN в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="42f64-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="42f64-226">Фильтрация по выбранным каналам глобальной сети</span><span class="sxs-lookup"><span data-stu-id="42f64-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="42f64-227">Фильтрация по каналам WAN с превышением установленной емкости канала</span><span class="sxs-lookup"><span data-stu-id="42f64-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="42f64-228">Фильтрация по каналам WAN с использованием подготовленной пропускной способности</span><span class="sxs-lookup"><span data-stu-id="42f64-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="42f64-229">Фильтрация по каналам WAN с достижением критических уровней (использование пропускной способности, превышающее 90% пропускной способности канала WAN)</span><span class="sxs-lookup"><span data-stu-id="42f64-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="42f64-230">Фильтрация по типу канала WAN — связи сайтов сети, взаимосвязи между регионами и ссылки на сайте</span><span class="sxs-lookup"><span data-stu-id="42f64-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="42f64-231">Фильтрация по области сети</span><span class="sxs-lookup"><span data-stu-id="42f64-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="42f64-232">Приложения</span><span class="sxs-lookup"><span data-stu-id="42f64-232">Applications</span></span>

<span data-ttu-id="42f64-233">Анализатор использования полосы пропускания использует следующие два приложения (инструменты):</span><span class="sxs-lookup"><span data-stu-id="42f64-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="42f64-234">**Программы wanlinklogcollector. exe** это средство позволяет пользователю ввести необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="42f64-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="42f64-235">**BandwidthUtilizationAnalyzer. xlsm** отчет по электронной таблице Microsoft Excel автоматически запускается программой программы wanlinklogcollector. exe.</span><span class="sxs-lookup"><span data-stu-id="42f64-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="42f64-236">Это приложение позволяет пользователю применять фильтры к отчету, как показано далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="42f64-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="42f64-237">Этапы использования анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="42f64-238">Использование анализатора использования полосы пропускания состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="42f64-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="42f64-239">Сбор журналов, выполняемых с помощью программы wanlinklogcollector. exe</span><span class="sxs-lookup"><span data-stu-id="42f64-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="42f64-240">Настройка отчетов, выполняемых с помощью BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="42f64-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="42f64-241">Для конечных пользователей настоятельно рекомендуется запускать BandwidthUtilizationAnalyzer. xlsm вручную.</span><span class="sxs-lookup"><span data-stu-id="42f64-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="42f64-242">Запуск анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="42f64-243">Запустите программы wanlinklogcollector. exe из командной строки или с помощью проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="42f64-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="42f64-244">**Использование программы wanlinklogcollector. exe**</span><span class="sxs-lookup"><span data-stu-id="42f64-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="42f64-245">Использование программы wanlinklogcollector. exe состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="42f64-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="42f64-246">**Запись временной шкалы** Укажите временную шкалу, для которой необходимо создать отчет.</span><span class="sxs-lookup"><span data-stu-id="42f64-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="42f64-247">**Указание каталогов файлов** Предоставление сведений о расположении файлов</span><span class="sxs-lookup"><span data-stu-id="42f64-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="42f64-248">**Сбор журналов и запуск средства просмотра отчетов** Выполнение команды для создания отчета</span><span class="sxs-lookup"><span data-stu-id="42f64-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="42f64-249">Шаг 1: запись временной шкалы</span><span class="sxs-lookup"><span data-stu-id="42f64-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="42f64-250">Ведение журнала временной шкалы позволяет пользователю средства указать следующие сведения, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="42f64-251">**Дата начала** Это Дата начала временной шкалы, для которой создается отчет; Например, 1 августа 2010 г.</span><span class="sxs-lookup"><span data-stu-id="42f64-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="42f64-252">**Дата окончания** Это Дата окончания временной шкалы, для которой создается отчет; Например, 30 сентября 2010 г.</span><span class="sxs-lookup"><span data-stu-id="42f64-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Начальная и конечная даты в использовании полосы пропускания A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="42f64-254">Шаг 2. Указание каталогов файлов</span><span class="sxs-lookup"><span data-stu-id="42f64-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="42f64-255">Пользователь может указать следующие каталоги файлов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="42f64-256">**Расположение файлов журнала сервера** Расположение папки, в которой хранятся журналы сервера политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="42f64-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="42f64-257">Обычно это \<филесервер\> \\<выбора \аппсерверфилес\пдп. Fe\></span><span class="sxs-lookup"><span data-stu-id="42f64-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="42f64-258">**Расположение хранилища временных файлов** Расположение временного файла, в котором хранятся промежуточные файлы во время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="42f64-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Каталоги файлов в анал использования полосы пропускания](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="42f64-260">Обеспечьте достаточный доступ к файлам для журналов сервера и папку хранилища временных файлов для пользователя средства.</span><span class="sxs-lookup"><span data-stu-id="42f64-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="42f64-261">Шаг 3: сбор журналов и запуск средства просмотра отчетов</span><span class="sxs-lookup"><span data-stu-id="42f64-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="42f64-262">Для сбора журналов и запуска средства просмотра отчетов нажмите кнопку **выполнить** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="42f64-263">На этом этапе выполняется сбор необходимых данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-263">This step collects the required data.</span></span>

![Сбор данных в анали использования полосы пропускания](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="42f64-265">После успешного выполнения проверки входного сообщения отображается приведенное ниже сообщение.</span><span class="sxs-lookup"><span data-stu-id="42f64-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Журнала собранных уведомлений в утили пропускной способности](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="42f64-267">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="42f64-267">Click **OK**.</span></span> <span data-ttu-id="42f64-268">BandwidthUtilizationAnalyzer. xlsm автоматически запускается.</span><span class="sxs-lookup"><span data-stu-id="42f64-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="42f64-269">Следуйте инструкциям в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="42f64-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="42f64-270">Дополнительные сведения см. в разделе **using BandwidthUtilizationAnalyzer. xlsm** в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="42f64-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="42f64-271">Использование BandwidthUtilizationAnalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="42f64-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="42f64-272">Когда BandwidthUtilizationAnalyzer. xlsm запускается автоматически, нажмите кнопку **Обновить** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer. xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="42f64-274">При открытии папки с файлами выберите файл консолидировать. CSV из расположения, указанного в поле сообщение, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="42f64-275">Он также показывает расположение как **C:\temp**.</span><span class="sxs-lookup"><span data-stu-id="42f64-275">It also shows the location as **C:\Temp**.</span></span>

     ![Открытие папки в BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="42f64-277">Нажмите кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="42f64-277">Click **Import**.</span></span>

4. <span data-ttu-id="42f64-278">Графический график создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="42f64-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="42f64-279">Он доступен при исчезновении указателя рабочего стола в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="42f64-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Применение фильтров в представлении отчета.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="42f64-281">Применение фильтров к представлению отчета</span><span class="sxs-lookup"><span data-stu-id="42f64-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="42f64-282">Фильтры, которые можно применить к представлению отчета, как показано ниже, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Применение фильтров в представлении отчета.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="42f64-284">**Name (имя** ) Фильтрация по каналам WAN (фильтр находится в правой части диаграммы). Префикс указывает следующие типы ссылок; Ознакомьтесь с вертикальным (синим) полем:</span><span class="sxs-lookup"><span data-stu-id="42f64-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="42f64-285">**Сайт S** Связь WAN между сетевым сайтом и регионом сети</span><span class="sxs-lookup"><span data-stu-id="42f64-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="42f64-286">**Межсайтовый** Канал WAN между двумя сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="42f64-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="42f64-287">**Внутрихолдинговый** Канал WAN между двумя областями сети</span><span class="sxs-lookup"><span data-stu-id="42f64-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="42f64-288">**Превышено ограничение** Фильтрация по каналам глобальной сети, использование пропускной способности которых превышает емкость полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="42f64-289">**Критические уровни** Фильтрация по каналам глобальной сети, использование которых пропускной способности достигло 90% или превышает емкость полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="42f64-290">**Неиспользованный** Фильтрация по каналам глобальной сети, использование полосы пропускания которых было меньше 25% от емкости полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="42f64-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="42f64-291">**Тип ссылки** Фильтрация по следующим типам каналов WAN Links:</span><span class="sxs-lookup"><span data-stu-id="42f64-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="42f64-292">Тип **сетевого сайта**</span><span class="sxs-lookup"><span data-stu-id="42f64-292">**Network site** type</span></span>

   - <span data-ttu-id="42f64-293">Тип **межсайтового взаимодействия**</span><span class="sxs-lookup"><span data-stu-id="42f64-293">**Inter-site** type</span></span>

   - <span data-ttu-id="42f64-294">Тип **связи между регионами**</span><span class="sxs-lookup"><span data-stu-id="42f64-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="42f64-295">**Region (регион** ) Фильтрация по регионам сети</span><span class="sxs-lookup"><span data-stu-id="42f64-295">**Region** Filter by network region</span></span>

<span data-ttu-id="42f64-296">На следующих рисунках показаны ранее описанные фильтры.</span><span class="sxs-lookup"><span data-stu-id="42f64-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="42f64-297">Фильтрация по **имени**.</span><span class="sxs-lookup"><span data-stu-id="42f64-297">Filter by **Name**.</span></span> <span data-ttu-id="42f64-298">Выберите список ссылок, которые должны отображаться на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="42f64-298">Select the list of links that need to be displayed in the graph.</span></span>

![Фильтрация по имени в BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="42f64-300">Фильтрация по **превышению лимита**.</span><span class="sxs-lookup"><span data-stu-id="42f64-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="42f64-301">Выберите **true** , чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="42f64-301">Select **True** to enforce the filter.</span></span>

![Фильтрация по превышению предельного значения.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="42f64-303">Фильтрация по **критическим уровням**.</span><span class="sxs-lookup"><span data-stu-id="42f64-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="42f64-304">Выберите **true** , чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="42f64-304">Select **True** to enforce the filter.</span></span>

![Фильтрация по критическим уровням.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="42f64-306">Отфильтровать по **в разделе используется**.</span><span class="sxs-lookup"><span data-stu-id="42f64-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="42f64-307">Выберите **true** , чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="42f64-307">Select **True** to enforce the filter.</span></span>

![Фильтрация по заданному принципу использования.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="42f64-309">Фильтрация по **типу ссылки**.</span><span class="sxs-lookup"><span data-stu-id="42f64-309">Filter by **Link Type**.</span></span> <span data-ttu-id="42f64-310">Выберите тип или типы, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="42f64-310">Select the type or types that need to be displayed.</span></span>

![Фильтрация по типу ссылки.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="42f64-312">Фильтрация по **регионам**.</span><span class="sxs-lookup"><span data-stu-id="42f64-312">Filter by **Region**.</span></span> <span data-ttu-id="42f64-313">Выберите список регионов, ссылки на которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="42f64-313">Select a list of regions whose links need to be displayed.</span></span>

![Фильтрация по регионам.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="42f64-315">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-315">Requirements</span></span>

- <span data-ttu-id="42f64-316">Платформа .NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="42f64-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="42f64-317">Microsoft Excel 2010 или Excel 2007</span><span class="sxs-lookup"><span data-stu-id="42f64-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="42f64-318">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-318">Summary</span></span>

<span data-ttu-id="42f64-319">Анализатор использования полосы пропускания используется для отображения использования пропускной способности звука для трафика UC в сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="42f64-320">Это средство можно использовать для отправки отчетов об использовании пропускной способности видео в сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="42f64-321">Вызов Parkometer</span><span class="sxs-lookup"><span data-stu-id="42f64-321">Call Parkometer</span></span>
<span data-ttu-id="42f64-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="42f64-323">Call Parkometer — это приложение командной строки, предоставляющее простой доступ к базе данных орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="42f64-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-324">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-324">Description</span></span>

<span data-ttu-id="42f64-325">Parkometer вызовов — это средство для отслеживания приостановленных звонков в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="42f64-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="42f64-326">Он также собирает статистику по орбитам и использованию сервера парковки вызовов (CPS).</span><span class="sxs-lookup"><span data-stu-id="42f64-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="42f64-327">Это средство командной строки предоставляет доступ для чтения и записи к базе данных SQL Server орбиты CPS с локального или удаленного подключенного компьютера.</span><span class="sxs-lookup"><span data-stu-id="42f64-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="42f64-328">Все параметры являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="42f64-328">All options are mutually exclusive.</span></span> <span data-ttu-id="42f64-329">Синтаксис командной строки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="42f64-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="42f64-330">параметр **-o** — список всех диапазонов орбиты, настроенных для этого пула.</span><span class="sxs-lookup"><span data-stu-id="42f64-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="42f64-331">параметр **-n** — перечисляет все используемые на данный момент орбиты в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="42f64-332">Отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="42f64-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="42f64-333">Универсальный код ресурса (URI) SIP и паркующего;.</span><span class="sxs-lookup"><span data-stu-id="42f64-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="42f64-334">Имя узла сервера публикаций Contribute, в котором приостановлен звонок.</span><span class="sxs-lookup"><span data-stu-id="42f64-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="42f64-335">Метка времени приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="42f64-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="42f64-336">параметр **-f** — отображает число свободных орбит в пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="42f64-337">**параметр- \<r\> n** — содержит \<n\> последних приостановленных звонков.</span><span class="sxs-lookup"><span data-stu-id="42f64-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="42f64-338">Отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="42f64-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="42f64-339">Универсальный код ресурса SIP SIP.</span><span class="sxs-lookup"><span data-stu-id="42f64-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="42f64-340">URI SIP паркующего;.</span><span class="sxs-lookup"><span data-stu-id="42f64-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="42f64-341">Имя узла сервера публикаций Contribute, в котором был приостановлен вызов.</span><span class="sxs-lookup"><span data-stu-id="42f64-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="42f64-342">Метка времени получения или удаления вызова.</span><span class="sxs-lookup"><span data-stu-id="42f64-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="42f64-343">параметр **–\<t\> n** — тестирует резервирование орбиты в базе данных, чтобы показать случайные значения назначенных номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="42f64-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-344">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-344">Output</span></span>

<span data-ttu-id="42f64-345">В зависимости от входных параметров, указанных в командной строке, вызовите Parkometer отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="42f64-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="42f64-346">Все диапазоны орбит, настроенные для этого пула</span><span class="sxs-lookup"><span data-stu-id="42f64-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="42f64-347">Приостановленные звонки</span><span class="sxs-lookup"><span data-stu-id="42f64-347">Currently parked calls</span></span>

- <span data-ttu-id="42f64-348">Количество свободных (доступных) орбит</span><span class="sxs-lookup"><span data-stu-id="42f64-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="42f64-349">Недавно приостановленные звонки</span><span class="sxs-lookup"><span data-stu-id="42f64-349">Recently parked calls</span></span>

- <span data-ttu-id="42f64-350">Зарезервированные орбиты для тестирования единообразных и случайных значений орбиты</span><span class="sxs-lookup"><span data-stu-id="42f64-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-351">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-351">Purpose</span></span>

<span data-ttu-id="42f64-352">Средство CPS предназначено для предоставления доступа к базе данных CPS с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="42f64-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="42f64-353">Администратор может просматривать использование CPS и определять число орбит, назначенных пулу.</span><span class="sxs-lookup"><span data-stu-id="42f64-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-354">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-354">Requirements</span></span>

<span data-ttu-id="42f64-355">Если это средство запущено на том же компьютере, где установлен сервер публикаций Contribute, никаких требований не существует.</span><span class="sxs-lookup"><span data-stu-id="42f64-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="42f64-356">Если это средство запущено на удаленном компьютере, то база данных SQL Server, используемая Skype для бизнеса Server 2015, должна быть настроена на разрешение удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="42f64-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="42f64-357">Для подключения к SQL Server с помощью Parkometer вызовов необходимо настроить строку подключения к базе данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="42f64-358">Эта строка подключения к базе данных SQL Server определена в файле конфигурации **parkometer. exe. config**. Он должен размещаться в том же каталоге, где находится parkometer. exe.</span><span class="sxs-lookup"><span data-stu-id="42f64-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="42f64-359">Приведенный ниже XML-файл является примером parkometer. exe. config. Параметры, которые необходимо настроить — это имя пользователя (например, Мидомаин\администратор), пароль (например, мипассворд) и имя узла (например, MyServer).</span><span class="sxs-lookup"><span data-stu-id="42f64-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="42f64-360">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-360">Examples</span></span>

<span data-ttu-id="42f64-361">Развернутые диапазоны орбиты: параметр – o содержит список всех диапазонов орбиты, настроенных для этого пула, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Диапазоны орбиты в вызове Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="42f64-363">В настоящее время приостановленные вызовы: параметр – n перечисляет все используемые на данный момент орбиты на этом пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Приостановленные вызовы в Parkometer вызовов.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="42f64-365">Число свободных орбит: параметр – f содержит число свободных орбит в пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Свободные орбиты в вызове Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="42f64-367">Недавно приостановленные звонки: параметр – r \<n\> содержит \<n\> последних приприпаркованных вызовов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Недавно припаркованные вызовы в вызове Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="42f64-369">Тестовое резервирование орбиты: \<параметр\> -t n тестирует резервирование орбиты в базе данных, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Протестируйте резервирование орбит в Parkometer вызовов.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="42f64-371">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-371">Summary</span></span>

<span data-ttu-id="42f64-372">Call Parkometer — это средство командной строки, предоставляющее подробные сведения о сервере парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="42f64-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="42f64-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="42f64-373">DBAnalyze</span></span>
<span data-ttu-id="42f64-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="42f64-375">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-375">Description</span></span>

<span data-ttu-id="42f64-376">DBAnalyze — это средство командной строки, помогающее администраторам собирать отчеты анализа о базах данных Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="42f64-377">В DBAnalyze имеются следующие режимы: диагностика, данные пользователей, конференц-связи, MCUs и фрагментация дисков:</span><span class="sxs-lookup"><span data-stu-id="42f64-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="42f64-378">**Диагностический режим** Создает отчет, содержащий сведения о таблицах (число записей, фрагментация, размер данных, и размер индекса), размерах файлов данных и журналов, время последнего резервного копирования и распространения контактных лиц между серверами с Microsoft Office Communications Server, средним числом разрешений, контактами, контейнерами, подписками, публикациями, конечными точками на пользователя, неправильной находящимися пользователями, пользователями, которые не могут маршрутизироваться, средним числом конференций, запланированных для пользователей и версия базы данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42f64-379">Выполнение диагностического режима может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="42f64-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="42f64-380">**Режим данных пользователя** Сообщает сведения о контактах, контейнерах, подписках, публикациях, разрешениях и группах контактов для указанного пользователя или для пользователей, имеющих этого пользователя в списках контактов и разрешений.</span><span class="sxs-lookup"><span data-stu-id="42f64-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="42f64-381">В этом режиме также выводится сводная информация о конференциях, на которые пользователь организует или приглашает.</span><span class="sxs-lookup"><span data-stu-id="42f64-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="42f64-382">**Режим конференции** Сообщает подробные данные о конкретной конференции, в том числе сведения о времени расписания для Конференции, список приглашений, список типов мультимедиа, разрешенных для Конференции, активные MCUs (единицы управления MultiPoint), список активных участников и состояние сигналов каждого участника.</span><span class="sxs-lookup"><span data-stu-id="42f64-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="42f64-383">**Расшифровка идентификатора собрания** Декодирует идентификатор собрания для телефонной сети общего пользования (PSTN), указанный с помощью коммутатора **/pstnid** , но не подключается к внутреннему серверу для получения подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="42f64-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="42f64-384">**Разрешение конференции** Декодирует идентификатор собрания PSTN, указанный с помощью параметра **/pstnid** , и отображает сведения о конференции, указанной идентификатором.</span><span class="sxs-lookup"><span data-stu-id="42f64-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="42f64-385">**Режим MCUs** Сообщает идентификатор, тип мультимедиа, URL-адрес, состояние пульса, нагрузку на конференцию и загрузку участников для каждого MCU в пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="42f64-386">**Режим фрагментации диска** Отображает состояние фрагментации всех дисков.</span><span class="sxs-lookup"><span data-stu-id="42f64-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="42f64-387">Это средство можно использовать для диагностики различных проблем или для оказания помощи администратору по планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="42f64-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="42f64-388">Например, если большинство пользователей, размещенных на сервере A, выбирают пользователей, размещенных на сервере б, в качестве их контактов, администратор может переместить пользователей на сервер а на сервер б, чтобы уменьшить трафик между серверами.</span><span class="sxs-lookup"><span data-stu-id="42f64-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-389">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-389">Output</span></span>

<span data-ttu-id="42f64-390">Это средство выводит предопределенные отчеты о базе данных Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="42f64-391">**Путь**:%ProgramFiles%\Skype для бизнеса Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="42f64-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-392">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-392">Purpose</span></span>

<span data-ttu-id="42f64-393">Чтобы установить Dbanalyze. exe, скопируйте его в локальную папку и запустите средство.</span><span class="sxs-lookup"><span data-stu-id="42f64-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="42f64-394">Чтобы использовать средство, выполните приведенную ниже команду в командной строке.</span><span class="sxs-lookup"><span data-stu-id="42f64-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="42f64-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Ниже приведены описания параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="42f64-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Параметры командной строки для Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="42f64-397">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-397">Requirements</span></span>

 <span data-ttu-id="42f64-398">**Computer (компьютер** ) DBAnalyze можно запустить только с компьютера, присоединенного к домену, на котором установлен Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="42f64-399">**Network (сеть** ) Компьютер должен иметь возможность подключения к серверной базе данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="42f64-400">**Программное обеспечение** Перед запуском DBAnalyze необходимо установить компоненты программного обеспечения Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="42f64-401">**Users (пользователи** ) В приведенной ниже таблице указаны администраторы, у которых есть необходимые разрешения на доступ к базам данных Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Таблица разрешений для Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="42f64-403">Локальная учетная запись администратора необходима для **/Report: режим диска** .</span><span class="sxs-lookup"><span data-stu-id="42f64-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-404">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-404">Examples</span></span>

<span data-ttu-id="42f64-405">Ниже приведены примеры допустимых команд Dbanalyze. exe.</span><span class="sxs-lookup"><span data-stu-id="42f64-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="42f64-406">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-406">Summary</span></span>

<span data-ttu-id="42f64-407">Дбанализер позволяет администраторам быстро и легко анализировать базы данных Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="42f64-408">Импорт данных службы хранилища</span><span class="sxs-lookup"><span data-stu-id="42f64-408">Import Storage Service Data</span></span>
<span data-ttu-id="42f64-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="42f64-410">Средство Импортсторажесервицедата Resource Kit позволяет повторно импортировать данные очередей и конечных точек, которые были удалены из службы хранения (LYSS), обратно в службу хранения.</span><span class="sxs-lookup"><span data-stu-id="42f64-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-411">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-411">Description</span></span>

<span data-ttu-id="42f64-412">Данные, удаляемые из службы хранилища, могли быть автоматически (периодически) на основе состояния элемента очереди или размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="42f64-413">Это могло произойти из-за вызова командлета отработки отказа пула вручную или командлета Сторажесервицефуллфлуш (который вызывается командлетом отработки отказа пула).</span><span class="sxs-lookup"><span data-stu-id="42f64-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="42f64-414">Обратите внимание, что в идеале данные не будут повторно импортироваться, если размер базы данных службы хранения (LYSS) на интерфейсных серверах переднего плана находится выше обычного уровня, так как это может привести к тому, что все данные будут экспортированы обратно. Кроме того, все проблемы, которые могут возникать при возникновении ошибок при увеличении очереди службы хранения, должны быть решены (например, ошибки конечной точки Exchange, проблемы с сетью или другие проблемы).</span><span class="sxs-lookup"><span data-stu-id="42f64-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="42f64-415">**Сценарий 1:** при отработке отказа пула файлы могут удаляться из службы хранилища для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="42f64-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="42f64-416">После завершения отработки отказа необходимо запустить средство для повторного импорта данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="42f64-417">**Сценарий 2:** данные очищаются автоматически каждый день или в ответ на базу данных службы хранилища, превышающие определенные пороговые значения размера (например, 60%, 80%, 90% Full).</span><span class="sxs-lookup"><span data-stu-id="42f64-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="42f64-418">Эти автоматически удаляемые данные должны повторно импортироваться администратором регулярно.</span><span class="sxs-lookup"><span data-stu-id="42f64-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="42f64-419">В приведенной выше ситуации, если пакет мониторинга SCOM не развернут, существуют события для службы хранилища Skype для бизнеса Server, связанные с очисткой данных из службы хранилища.</span><span class="sxs-lookup"><span data-stu-id="42f64-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="42f64-420">Идентификаторы событий 32075 (операция полного сброса начинается), 32076 (полная очистка завершена), 32082 (начато копирование на уровне обслуживания), 32083 (очистка на уровне обслуживания завершена), 32089 (очистка выполнена из-за заполнения базы данных).</span><span class="sxs-lookup"><span data-stu-id="42f64-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="42f64-421">Обратите внимание, что эти коды событий соответствуют выпуску RTM.</span><span class="sxs-lookup"><span data-stu-id="42f64-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="42f64-422">Когда администратор видит эти события, это означает, что существуют файлы, которые были удалены. Эти данные следует регулярно импортировать обратно с помощью этого средства, например один раз в неделю.</span><span class="sxs-lookup"><span data-stu-id="42f64-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="42f64-423">При выпуске веб-службы, если развернут пакет мониторинга работоспособности SCOM для Skype для бизнеса Server, появляются новые оповещения, которые попросите администратора повторно импортировать данные, которые были удалены, обратно в службу хранилища.</span><span class="sxs-lookup"><span data-stu-id="42f64-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="42f64-424">В журнале событий на сервере переднего плана, вызвавшем оповещение, появится соответствующее событие.</span><span class="sxs-lookup"><span data-stu-id="42f64-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="42f64-425">Событие предоставит описание родительского пути, в котором находятся файлы данных с очисткой, а также количество файлов, соответствующих условиям оповещения.</span><span class="sxs-lookup"><span data-stu-id="42f64-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="42f64-426">Критерий оповещения состоит в том, что существует X или более файлов по отношению к определенному родительскому пути по крайней мере по крайней мере по крайней мере по оси Y дней (где X и Y задаются в Сторажесервице, но их можно переопределить, изменив файл АППКОНФИГ). Два примера событий, которые могут вызывать оповещение о работоспособности, показаны ниже, а их родительский путь отличается.</span><span class="sxs-lookup"><span data-stu-id="42f64-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="42f64-427">Один из возможных вариантов — файловый ресурс веб-службы, а другая возможность — локальный каталог данных приложений для каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="42f64-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="42f64-428">(например, К:\програмдата\микрософт\скипе для бизнеса Server 2015 \ Сторажесервице).</span><span class="sxs-lookup"><span data-stu-id="42f64-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="42f64-429">После этого администратор запустит это средство reskit.</span><span class="sxs-lookup"><span data-stu-id="42f64-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="42f64-430">Это средство увеличит нагрузку ЦП и ввода-вывода на интерфейсном сервере, на котором она работает, а также на других интерфейсных серверах, в случае, если данные не принадлежат внешнему интерфейсу, на котором выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="42f64-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="42f64-431">Мы рекомендуем запускать это средство, если на интерфейсных серверах не загружается высокая загрузка ЦП и ввода-вывода, например, в нерабочее время.</span><span class="sxs-lookup"><span data-stu-id="42f64-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="42f64-432">Во вторых, это средство может выполнить из 2 до 3 минут, чтобы импортировать один файл данных.</span><span class="sxs-lookup"><span data-stu-id="42f64-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="42f64-433">Помните об этом при оценке времени, в течение которого будет выполняться средство.</span><span class="sxs-lookup"><span data-stu-id="42f64-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="42f64-434">Подробный файл журнала, создаваемый средством, по умолчанию отображается в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="42f64-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="42f64-435">Удалите его, если нет сообщений об ошибках, так как файл журнала может содержать не более десятков МБ.</span><span class="sxs-lookup"><span data-stu-id="42f64-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![События журнала событий для хранилища событий сервера.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="42f64-437">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-437">Requirements</span></span>

<span data-ttu-id="42f64-438">Установите средства набора ресурсов Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="42f64-439">Средство запускается на подключенных к домену компьютерах, на которых установлены оболочки управления Skype для бизнеса Server и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="42f64-440">Средство использует командлет из командной консоли, чтобы определить все серверы переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="42f64-441">Во вторых случаях средство необходимо запускать на компьютере в пуле, где установлена база данных **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="42f64-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="42f64-442">Эта база данных используется средством для получения расположения общего файлового ресурса WEBSERVICE для пула.</span><span class="sxs-lookup"><span data-stu-id="42f64-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="42f64-443">Кроме того, перед использованием средства каждый сервер переднего плана должен сначала включить удаленное взаимодействие Windows PowerShell с помощью командлета **Enable-псремотинг** на каждом сервере переднего плана, а также на компьютере, с которого выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="42f64-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="42f64-444">В противном случае удаленные команды Windows PowerShell из этого средства завершатся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="42f64-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="42f64-445">Удаленное взаимодействие Windows PowerShell может быть отключено на всех серверах переднего плана в пуле после его завершения.</span><span class="sxs-lookup"><span data-stu-id="42f64-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="42f64-446">Наконец, учетная запись или учетные данные, вызывающие средство, должны иметь разрешение на чтение и запись для общего файлового ресурса WebService для пула, в котором выполняется это средство.</span><span class="sxs-lookup"><span data-stu-id="42f64-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="42f64-447">В противном случае средство завершится с ошибками разрешений ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="42f64-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="42f64-448">В Windows Server 2012 удаленное взаимодействие Windows PowerShell включено по умолчанию, но не в операционной системе Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="42f64-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-449">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-449">Examples</span></span>

```console
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
```

## <a name="lcssync"></a><span data-ttu-id="42f64-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="42f64-450">LCSSync</span></span>
<span data-ttu-id="42f64-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="42f64-452">Средство LCSSync помогает развернуть программное обеспечение для связи Skype для бизнеса Server 2015 в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="42f64-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="42f64-453">Это средство используется для синхронизации пользователей и групп из различных лесов пользователя как объект контакта доменных служб Active Directory в центральном лесу, где установлен Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-454">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-454">Description</span></span>

 <span data-ttu-id="42f64-455">LCSSync использует синхронизированные объекты контактов доменных служб Active Directory в центральном лесу, чтобы разрешить пользователям Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="42f64-456">Для предоставления единого входа основная учетная запись пользователя должна быть сопоставлена с объектом контакта доменных служб Active Directory в центральном лесу для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="42f64-457">Это средство помогает выполнить это сопоставление.</span><span class="sxs-lookup"><span data-stu-id="42f64-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="42f64-458">Это средство предоставляет шаблоны для создания агентов управления на сервере Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="42f64-459">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-459">Summary</span></span>

<span data-ttu-id="42f64-460">Средство LCSSync помогает развертывать Skype для бизнеса Server 2015 в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="42f64-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="42f64-461">Консоль поиска пользователей</span><span class="sxs-lookup"><span data-stu-id="42f64-461">Lookup User Console</span></span>
<span data-ttu-id="42f64-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="42f64-463">Средство LookupUserConsole отображает сведения о маршрутизации внутренних пользователей Skype для бизнеса Server для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="42f64-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="42f64-464">Эта информация может быть полезной для поддержки корпорацией Майкрософт личных сведений при диагностике проблем развертывания и маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="42f64-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-465">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-465">Description</span></span>

 <span data-ttu-id="42f64-466">При выполнении LookupUserConsole. exe откроется Командная строка, которая принимает адреса SIP и пытается отобразить сведения о маршрутизации внутренних Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="42f64-467">Введите **Exit** , чтобы завершить работу средства LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="42f64-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-468">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-468">Requirements</span></span>

<span data-ttu-id="42f64-469">Установите пакет ресурсов Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="42f64-470">Средство запускается на подключенных к домену компьютерах, на которых установлен Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-471">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-471">Examples</span></span>

<span data-ttu-id="42f64-472">C:\Program Files\Skype for Business Server 2015 \ ResKit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="42f64-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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
```

## <a name="msturnping"></a><span data-ttu-id="42f64-473">мстурнпинг</span><span class="sxs-lookup"><span data-stu-id="42f64-473">MsTurnPing</span></span>
<span data-ttu-id="42f64-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="42f64-475">Средство Мстурнпинг позволяет администратору программного обеспечения для обмена мгновенными сообщениями Skype для бизнеса Server 2015 проверять состояние серверов, на которых работает служба проверки подлинности аудио-и видеоданных, а также серверы, на которых выполняются службы политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="42f64-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-476">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-476">Description</span></span>

<span data-ttu-id="42f64-477">Средство Мстурнпинг позволяет администратору программного обеспечения для обмена мгновенными сообщениями Skype для бизнеса Server 2015 проверять состояние серверов, на которых работает служба проверки подлинности аудио-и видеоданных, а также серверы, на которых выполняются службы политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="42f64-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="42f64-478">Средство позволяет администратору выполнять следующие тесты:</span><span class="sxs-lookup"><span data-stu-id="42f64-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="42f64-479">Тест пограничного сервера аудио-и видеоданных: средство выполняет тестирование для всех пограничных серверов аудио-и видеоданных в топологии, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="42f64-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="42f64-480">Проверка того, что служба аудио-и видеоаутентификации Skype для бизнеса Server запущена и может выдать правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="42f64-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="42f64-481">Проверка того, что служба аудио-и видеоданных Skype для бизнеса Server запущена и может успешно выделять ресурсы на внешнем пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="42f64-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="42f64-482">Проверка службы политики пропускной способности: средство выполняет тесты для всех серверов, на которых выполняются службы политики пропускной способности в топологии, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="42f64-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="42f64-483">Проверка того, что служба политики пропускной способности Skype для бизнеса Server (проверка подлинности) запущена и может выдать правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="42f64-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="42f64-484">Проверка того, что запущена служба политики пропускной способности Skype для бизнеса Server (ядро), и может успешно выполнить проверку пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="42f64-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="42f64-485">Это средство необходимо запускать на компьютере, который входит в топологию и на котором установлено локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="42f64-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-486">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-486">Output</span></span>

<span data-ttu-id="42f64-487">Средство выводит результаты каждой операции.</span><span class="sxs-lookup"><span data-stu-id="42f64-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="42f64-488">Если выполняется тест **аудиовидеоеджесервер** , выводятся следующие данные средства:</span><span class="sxs-lookup"><span data-stu-id="42f64-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="42f64-489">Результаты тестирования компьютеров, которые обеспечивают службу проверки подлинности в Skype для бизнеса Server 2015 в топологии</span><span class="sxs-lookup"><span data-stu-id="42f64-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="42f64-490">Результаты тестирования компьютеров, которые обеспечивают пограничную службу аудио-и видеоданных в Skype для бизнеса Server 2015 в топологии</span><span class="sxs-lookup"><span data-stu-id="42f64-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="42f64-491">Если выполняется тест **бандвидсполицисервер** , выводятся следующие данные средства:</span><span class="sxs-lookup"><span data-stu-id="42f64-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="42f64-492">Результаты тестирования компьютеров, которые обеспечивают службу политики пропускной способности Skype для бизнеса Server 2015 (проверка подлинности) в топологии</span><span class="sxs-lookup"><span data-stu-id="42f64-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="42f64-493">Результаты тестирования компьютеров, которые обеспечивают службу политики пропускной способности Skype для бизнеса Server 2015 (ядро) в топологии</span><span class="sxs-lookup"><span data-stu-id="42f64-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-494">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-494">Requirements</span></span>

- <span data-ttu-id="42f64-495">Это средство необходимо запускать на компьютере, который находится в топологии и имеет локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="42f64-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="42f64-496">Средство должно быть запущено от имени администратора, имеющего доступ к локальному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="42f64-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-497">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-497">Examples</span></span>

<span data-ttu-id="42f64-498">Ниже приведен пример входных данных средства.</span><span class="sxs-lookup"><span data-stu-id="42f64-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="42f64-499">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-499">Summary</span></span>

<span data-ttu-id="42f64-500">Это средство может быть ценным ресурсом для администраторов Skype для бизнеса Server 2015, которые хотят проверить состояние серверов, на которых работают службы политики аудио-и видеосвязи и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="42f64-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="42f64-501">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="42f64-501">Network Configuration Viewer</span></span>
<span data-ttu-id="42f64-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="42f64-503">Средство просмотра конфигурации сети может использоваться администраторами системы обмена мгновенными сообщениями Skype для бизнеса Server 2015 для просмотра топологии сети контроля допуска звонков (CAC) для предприятия, подготовленного для поддержки сеансов связи в реальном времени, таких как голосовые и видеозвонки на основе указанной емкости полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="42f64-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="42f64-504">В Skype для бизнеса Server 2015 администраторы определяют политики CAC, которые применяются службами политики пропускной способности, установленными с помощью Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-505">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-505">Description</span></span>

<span data-ttu-id="42f64-506">Средство просмотра конфигурации сети (Нетворкконфигуратионвиевер. exe) позволяет администраторам выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="42f64-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="42f64-507">Загрузка и просмотр топологии сети CAC из развертывания Skype для бизнеса Server 2015 в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="42f64-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="42f64-508">Загрузка и просмотр топологии сети CAC из файла журнала сервера политики пропускной способности в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="42f64-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="42f64-509">Сохраните и сохраните топологию сети CAC в формате XML на диске.</span><span class="sxs-lookup"><span data-stu-id="42f64-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="42f64-510">Сохраните и сохраните схему топологии сети CAC в формате JPG или BMP.</span><span class="sxs-lookup"><span data-stu-id="42f64-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="42f64-511">Просмотр данных конфигурации топологии сети CAC.</span><span class="sxs-lookup"><span data-stu-id="42f64-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="42f64-512">Просмотр топологии сети CAC в стиле представления дерева.</span><span class="sxs-lookup"><span data-stu-id="42f64-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="42f64-513">Определите настраиваемые соединители для связей топологии сети CAC (например, "сайт-регион", "между регионами" и "между сайтами").</span><span class="sxs-lookup"><span data-stu-id="42f64-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="42f64-514">Просмотр сведений о сайте топологии сети CAC, сведений о регионе и о подготовленных политиках пропускной способности и сетевых соединениях.</span><span class="sxs-lookup"><span data-stu-id="42f64-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-515">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-515">Purpose</span></span>

<span data-ttu-id="42f64-516">Просмотр ссылок на топологию сети CAC в графическом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="42f64-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-517">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-517">Examples</span></span>

 <span data-ttu-id="42f64-518">**Загрузка и просмотр топологии сети CAC с помощью развертывания Skype для бизнеса server 2015 в графическом формате**: Skype для бизнеса Server 2015 администраторы могут загружать и просматривать конфигурацию ТОПОЛОГИИ сети CAC на любом компьютере Skype для бизнеса Server 2015 с помощью параметра **Конфигурация сети** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="42f64-519">Средство не сможет скачать или просмотреть такую конфигурацию при развертывании на компьютере, на котором нет подключения к хранилищу конфигураций Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Загрузка конфигурации сети.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="42f64-521">**Загрузка и просмотр топологии сети CAC из файла журнала сервера политики пропускной способности в графическом формате:** Серверы политики пропускной способности Skype для бизнеса Server 2015. Сохраните топологию сети CAC в качестве части механизма ведения журнала в расположении общего файлового ресурса Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="42f64-522">Skype для бизнеса Server 2015 администраторы могут просматривать такой файл в графическом формате с помощью параметра **Конфигурация Open Network** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Открытие файла журнала сервера политики пропускной способности.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="42f64-524">Сохраните и сохраните топологию сети CAC в формате XML на диске: Skype для бизнеса Server 2015 администраторы могут сохранить файл конфигурации топологии сети CAC в формате XML с помощью параметра **сохранить копию конфигурации сети** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="42f64-525">Сохраненный файл конфигурации можно использовать в автономном режиме для просмотра в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="42f64-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Сохранение конфигурации сети в виде XML-файла.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="42f64-527">Сохранение и **Сохранение схемы топологии** сети CAC в формате JPG или BMP: Skype для бизнеса Server 2015 администраторы могут сохранить конфигурацию ТОПОЛОГИИ сети CAC в графическом формате (форматы файлов JPG и BMP), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Сохранение конфигурации сети как изображения.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="42f64-529"><strong>Просмотр данных конфигурации топологии сети CAC:</strong> Skype для бизнеса Server 2015 администраторы могут просматривать связанные данные конфигурации сети, такие как регионы сети, сетевые сайты, профили пропускной способности и IP-адреса подсетей сайтов в текстовом формате, с помощью параметра Просмотр данных конфигурации сети, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Просмотр данных конфигурации сети.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="42f64-531">**Просмотр топологии сети CAC в стиле представления дерева:** Skype для бизнеса Server 2015 администраторы могут просматривать связанные данные конфигурации сети в графическом стиле представления дерева, используя панель управления в левой части окна инструментов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Просмотр данных конфигурации сети в виде дерева.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="42f64-533">**Определите настраиваемые соединители для связей топологии сети CAC (например, "сайт-регион", "между регионами" и "сеть-сеть"):** Skype для бизнеса Server 2015 администраторы могут определять настраиваемые графические соединители для каналов связи WAN с конфигурацией сети с помощью параметра Settings, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="42f64-534">Это позволяет отличать различные типы сетевых связей, подготовленных в конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="42f64-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Средства](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="42f64-536">**Просмотр сведений о сайте топологии сети CAC, сведений о регионе и подготовленных политиках пропускной способности:** Skype для бизнеса Server 2015 администраторы могут просматривать связанные сведения о области сети CAC, сведения о сайте и сведения о подготовке пропускной способности CAC с помощью параметров, показанных ниже.</span><span class="sxs-lookup"><span data-stu-id="42f64-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="42f64-537">(Например, щелкните **сведения** в сетевом регионе или в объекте сетевого сайта.)</span><span class="sxs-lookup"><span data-stu-id="42f64-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Определение настраиваемых соединителей для сети;](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="42f64-539">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-539">Summary</span></span>

<span data-ttu-id="42f64-540">Это средство может быть ценным ресурсом для пользователей Skype для бизнеса Server 2015, которые хотят просмотреть топологию сети CAC для развертывания в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="42f64-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="42f64-541">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="42f64-541">Response Group Agent Live</span></span>
<span data-ttu-id="42f64-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="42f64-543">Приложение группы ответа дает агентам возможность получать доступ к полезной информации в режиме реального времени с помощью встроенной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="42f64-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="42f64-544">К сожалению, графическое представление этих данных недоступно вне приложения.</span><span class="sxs-lookup"><span data-stu-id="42f64-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="42f64-545">Средство "Live Resource Kit Agent Agent" решает эту проблему, предоставляя простой и графический способ доступа к этой информации, дополненный сведениями о программном обеспечении Skype для бизнеса в режиме реального времени, такими как присутствие других агентов.</span><span class="sxs-lookup"><span data-stu-id="42f64-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-546">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-546">Description</span></span>

<span data-ttu-id="42f64-547">Агент группы ответа Live — это приложение Windows, которое предоставляет функции входа и выхода, а также некоторые сведения в режиме реального времени (например, сведения о членстве в группах и текущем количестве звонков) для агентов группы ответа.</span><span class="sxs-lookup"><span data-stu-id="42f64-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="42f64-548">Она предназначена для расширенной версии страницы "группы агентов" (доступна в Skype для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="42f64-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-549">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-549">Purpose</span></span>

<span data-ttu-id="42f64-550">Приложение группы ответа ставит в очередь входящие вызовы, а затем направляет их в группы агентов.</span><span class="sxs-lookup"><span data-stu-id="42f64-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="42f64-551">Для принятия обоснованных решений о вызовах служб агенты могут получать доступ к сведениям о группах агентов в режиме реального времени, например о том, какие другие агенты доступны и сколько вызовов ожидают в каждой очереди.</span><span class="sxs-lookup"><span data-stu-id="42f64-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="42f64-552">Эта информация, изначально доступная только через службу группы ответа, становится доступной интуитивно понятным образом агентом группы ответа Live.</span><span class="sxs-lookup"><span data-stu-id="42f64-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="42f64-553">Возможности</span><span class="sxs-lookup"><span data-stu-id="42f64-553">Features</span></span>

<span data-ttu-id="42f64-554">Средство Live Agent Agent (агент группы ответа) построено на основе службы группы ответа и пакета SDK Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="42f64-555">Он предоставляет агентам группы ответа сведения и возможности, доступные в службе группы ответа (например, сведения о членстве в группах, присутствии других агентов и количестве ожидающих вызовов).</span><span class="sxs-lookup"><span data-stu-id="42f64-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="42f64-556">На приведенном ниже рисунке показан основной интерфейс агента группы ответа Live.</span><span class="sxs-lookup"><span data-stu-id="42f64-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Средство Live Agent Agent (агент группы ответа).](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="42f64-558">Для агентов в действующем агенте группы ответа доступны следующие три основные функции:</span><span class="sxs-lookup"><span data-stu-id="42f64-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="42f64-559">**Вход и выход:** В отличие от страницы "группы агентов" (доступного из Skype для бизнеса Server 2015), агент группы ответа Live позволяет только агентам выполнять вход или выход из всех групп агентов одновременно.</span><span class="sxs-lookup"><span data-stu-id="42f64-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="42f64-560">Это приложение предоставляет три быстрых способа для входа и выхода:</span><span class="sxs-lookup"><span data-stu-id="42f64-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="42f64-561">Нажмите кнопки Вход/выход (зеленая и красная) в приложении.</span><span class="sxs-lookup"><span data-stu-id="42f64-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="42f64-562">Щелкните правой кнопкой мыши значок System табло и выберите команду войти или выйти.</span><span class="sxs-lookup"><span data-stu-id="42f64-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="42f64-563">Использование настраиваемых сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="42f64-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="42f64-564">**Членство в группе:** Если выбрана группа агентов, Live Agent Agent (агент группы ответа) отображает список агентов в этой группе на правой панели.</span><span class="sxs-lookup"><span data-stu-id="42f64-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="42f64-565">Если Skype для бизнеса Server 2015 запущен на том же компьютере, что и это приложение, сведения о присутствии и карточка контакта отображаются в поле агент группы ответа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="42f64-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="42f64-566">Агенты могут отправлять мгновенные сообщения или вызывать другие агенты непосредственно из него.</span><span class="sxs-lookup"><span data-stu-id="42f64-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="42f64-567">**Статистика в режиме реального времени:** Агент группы ответа Live предоставляет статистику в режиме реального времени для всех групп агентов.</span><span class="sxs-lookup"><span data-stu-id="42f64-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="42f64-568">Частота обновления составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="42f64-568">The update frequency is one minute.</span></span> <span data-ttu-id="42f64-569">Когда группа ответа отвечает на вызов, рядом с именем группы добавляется визуальный индикатор с текущим количеством вызовов в очереди.</span><span class="sxs-lookup"><span data-stu-id="42f64-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="42f64-570">При приостановке указателя над группой также отображается самое большое время ожидания.</span><span class="sxs-lookup"><span data-stu-id="42f64-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-571">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-571">Requirements</span></span>

<span data-ttu-id="42f64-572">Для работы агента группы ответа в Live требуется .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="42f64-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="42f64-573">Кроме того, чтобы воспользоваться преимуществами функций присутствия и карточки контакта, необходимо установить Skype для бизнеса локально (и на работе).</span><span class="sxs-lookup"><span data-stu-id="42f64-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="42f64-574">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="42f64-574">Configuration</span></span>

<span data-ttu-id="42f64-575">Активный агент группы ответа можно изменить на индивидуальные настройки с помощью диалогового окна "Параметры" в приложении.</span><span class="sxs-lookup"><span data-stu-id="42f64-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="42f64-576">Кроме того, администратор может определить адрес узла по умолчанию, отредактировав непосредственно свойство Дефаулсостаддресс файла Ргажентливе. exe. config.</span><span class="sxs-lookup"><span data-stu-id="42f64-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="42f64-577">На приведенном ниже рисунке показано диалоговое окно "Параметры", которое агенты могут использовать для настройки адреса узла и сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="42f64-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="42f64-578">Для доступа к этому диалоговому окну нажмите кнопку Параметры в правом верхнем углу основного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="42f64-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Диалоговое окно "Параметры агента группы ответа".](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="42f64-580">В динамической конфигурации агента группы ответа можно настроить следующие три различных параметра:</span><span class="sxs-lookup"><span data-stu-id="42f64-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="42f64-581">Адрес узла: обычно это полное доменное имя веб-пула, которое принадлежит домашнему пулу агента.</span><span class="sxs-lookup"><span data-stu-id="42f64-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="42f64-582">Точный адрес службы группы ответа автоматически создается на заднем плане от этих сведений (путем добавления правильного пути после размещения узла).</span><span class="sxs-lookup"><span data-stu-id="42f64-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="42f64-583">Сочетания клавиш: можно изменить точные сочетания клавиш для входа и выхода.</span><span class="sxs-lookup"><span data-stu-id="42f64-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="42f64-584">Единственное ограничение состоит в том, что оба сочетания клавиш должны содержать клавишу Windows Logo (помимо по крайней мере еще одного ключа).</span><span class="sxs-lookup"><span data-stu-id="42f64-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="42f64-585">Начните с Windows: приложение может быть настроено на автоматический запуск с Windows.</span><span class="sxs-lookup"><span data-stu-id="42f64-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-586">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-586">Examples</span></span>

<span data-ttu-id="42f64-587">На приведенном ниже рисунке показано, как вызвать или отправить мгновенное сообщение другому агенту, щелкнув контакт правой кнопкой мыши в правой области.</span><span class="sxs-lookup"><span data-stu-id="42f64-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Выполнение вызова или отправка мгновенного сообщения.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="42f64-589">На приведенном ниже рисунке показано, как Live агент группы ответа отображает текущее число вызовов в очереди и самое большое время ожидания для всех входящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="42f64-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Просмотр сведений об очереди.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="42f64-591">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-591">Summary</span></span>

<span data-ttu-id="42f64-592">При быстром входе и выходе, членстве в группах и базовой статистике в режиме реального времени используются интересные функции агента группы ответа, которые доступны только вне приложения из службы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="42f64-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="42f64-593">С помощью средства "Live Resource Agent Agent" (агент группы ответа) администраторы Skype для бизнеса Server 2015 могут предоставлять свои агенты с помощью приложения Windows, позволяющего выполнять задачи быстрее и графически.</span><span class="sxs-lookup"><span data-stu-id="42f64-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="42f64-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="42f64-594">SEFAUtil</span></span>
<span data-ttu-id="42f64-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="42f64-596">SEFAUtil (дополнительная активация дополнительных компонентов расширения) — это средство командной строки, которое позволяет администраторам и агентам по связи Skype для бизнеса Server 2015 и агентам службы поддержки настраивать делегирование звонков, переадресацию вызовов, одновременных звонков параметры и групповые звонки для групповых звонков от имени пользователя Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="42f64-597">Кроме того, с помощью этого средства администраторы могут запрашивать параметры маршрутизации вызовов, опубликованные для определенного пользователя. Средство SEFAUtil позволяет администратору включать, отключать и изменять переадресацию вызовов или одновременно звонить от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="42f64-598">Администратор может указать целевой объект (в виде URI SIP) или использовать целевой объект, уже опубликованный пользователем.</span><span class="sxs-lookup"><span data-stu-id="42f64-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="42f64-599">Кроме того, это средство позволяет администраторам добавлять и удалять делегатов или участников группы звонков группы от имени пользователя. Это средство основано на Microsoft Unified Communications Managed API (UCMA) 3,0 и требует, чтобы администраторы создавали доверенное приложение в центральном хранилище управления для SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="42f64-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="42f64-600">SEFAUtil (дополнительный добавочный номер активации) позволяет администраторам Skype для бизнеса Server 2015 и агентам службы поддержки настраивать делегирование звонков, переадресацию вызовов, Одновременный звонок, параметры групповых звонков и групповую отправку звонков от имени Skype для пользователя Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="42f64-601">Это средство также позволяет администраторам запрашивать параметры маршрутизации вызовов, опубликованные для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-602">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-602">Description</span></span>

<span data-ttu-id="42f64-603">Текущей версией SEFAUtil является только средство командной строки; нет поддерживающего графического пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="42f64-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="42f64-604">Это средство основано на Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="42f64-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="42f64-605">Функции этого средства позволяют администраторам и агентам службы поддержки выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="42f64-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="42f64-606">Просмотр всех параметров маршрутизации вызовов для пользователя (включая переадресацию звонков, делегирование, Одновременный звонок, вызов по команде и групповые звонки)</span><span class="sxs-lookup"><span data-stu-id="42f64-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="42f64-607">Включение, отключение и изменение параметра переадресации вызовов (включая таймер "назначение" и "нет ответа")</span><span class="sxs-lookup"><span data-stu-id="42f64-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="42f64-608">Включение, отключение и изменение немедленных конфигураций пересылки вызовов</span><span class="sxs-lookup"><span data-stu-id="42f64-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="42f64-609">Включение, отключение и изменение параметров делегирования</span><span class="sxs-lookup"><span data-stu-id="42f64-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="42f64-610">Включение, отключение и изменение параметров группы звонков в группе</span><span class="sxs-lookup"><span data-stu-id="42f64-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="42f64-611">Новое в средстве SEFAUtil для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="42f64-612">Включение, отключение и изменение параметров одновременных звонков (включая назначение)</span><span class="sxs-lookup"><span data-stu-id="42f64-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="42f64-613">Новое в средстве SEFAUtil для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="42f64-614">Включение, отключение и изменение параметров ответа на групповые звонки</span><span class="sxs-lookup"><span data-stu-id="42f64-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="42f64-615">Новое в средстве SEFAUtil для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="42f64-616">Это средство имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="42f64-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="42f64-617">Поддерживается только для пользователей, размещенных в пуле Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="42f64-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="42f64-618">Массовое изменение параметров маршрутизации звонков для нескольких пользователей не поддерживается</span><span class="sxs-lookup"><span data-stu-id="42f64-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="42f64-619">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-619">Output</span></span>

<span data-ttu-id="42f64-620">Текущая версия этого средства предоставляет выходные данные только в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="42f64-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="42f64-621">Дополнительные сведения см. в разделе "примеры" Далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="42f64-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-622">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-622">Purpose</span></span>

<span data-ttu-id="42f64-623">Ниже приведены некоторые ключевые сценарии, в которых можно использовать это средство:</span><span class="sxs-lookup"><span data-stu-id="42f64-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="42f64-624">Боб является руководителем и перемещен в телефонную связь Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="42f64-625">У него есть делегирование в существующей системе УАТС.</span><span class="sxs-lookup"><span data-stu-id="42f64-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="42f64-626">В рамках перехода на Skype для бизнеса Server 2015 администратор может настроить маршрутизацию Боба в соответствии с существующей конфигурацией делегирования.</span><span class="sxs-lookup"><span data-stu-id="42f64-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="42f64-627">Алиса движется и осознает, что она ожидает важный звонок от одного из клиентов.</span><span class="sxs-lookup"><span data-stu-id="42f64-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="42f64-628">Однако она находится в отеле и не имеет доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="42f64-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="42f64-629">Она звонит в службу поддержки и запрашивает у нее все звонки, выполненные на свой номер рабочего телефона.</span><span class="sxs-lookup"><span data-stu-id="42f64-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="42f64-630">Сотрудники службы поддержки могут выполнять настройку от его имени.</span><span class="sxs-lookup"><span data-stu-id="42f64-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="42f64-631">Звонки Джо на свой рабочий номер будут передаются в мобильную голосовую почту, когда он работает; Тем не менее, некоторые из них работают правильно в других расположениях.</span><span class="sxs-lookup"><span data-stu-id="42f64-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="42f64-632">Специалист по технической поддержки может просматривать конфигурацию маршрутизации Джо и обнаруживать, что у Ивана есть одновременные звонки, настроенные на мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="42f64-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="42f64-633">Специалист запрашивает Иван о покрытии мобильного качества на своем офисе и может определить, что одновременное правило вызывает отдачу голосовых голосовых вызовов Джо на мобильную голосовую почту, если ее работа неудовлетворительна.</span><span class="sxs-lookup"><span data-stu-id="42f64-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="42f64-634">Майк — это новый сотрудник в компании Contoso, который присоединяется к новой команде, для которой все участники настроены на вызов команды, при включении поддержки Skype для бизнеса Server 2015 администратор может задать параметры группы звонков в качестве группы звонков, чтобы включить всех ее новых участников группы. Кроме того, администратор добавляет Майк в качестве участника группы звонков группы для каждого участника в своей команде.</span><span class="sxs-lookup"><span data-stu-id="42f64-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="42f64-635">Обслуживание клиентов в отделе кадров компании Contoso заключается в предоставлении личной службы для всех абонентов с момента первого звонка.</span><span class="sxs-lookup"><span data-stu-id="42f64-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="42f64-636">С учетом того, что все участники отдела располагаются близко друг к другу, и все телефоны в то же время с помощью командного вызова очень нарушают эту группу.</span><span class="sxs-lookup"><span data-stu-id="42f64-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="42f64-637">Чтобы обеспечить наилучшую службу, не нарушая участников группы, администратор Skype для бизнеса Server 2015 использует функцию отправки групповых вызовов.</span><span class="sxs-lookup"><span data-stu-id="42f64-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="42f64-638">Администратор добавляет всех участников отдела в группу раскладки и передает их в отделный номер группы раскладки.</span><span class="sxs-lookup"><span data-stu-id="42f64-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="42f64-639">Когда Samantha отсутствует на рабочем месте, Джо заметит его телефонный звонок и выберет на себя ответ на звонок со своего рабочего места.</span><span class="sxs-lookup"><span data-stu-id="42f64-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-640">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-640">Requirements</span></span>

<span data-ttu-id="42f64-641">Средство SEFAUtil можно запустить только на компьютере, который является частью пула доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="42f64-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="42f64-642">На этом компьютере должен быть установлен UCMA 3,0.</span><span class="sxs-lookup"><span data-stu-id="42f64-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="42f64-643">Для запуска средства необходимо создать в этом пуле новое доверенное приложение с ИДЕНТИФИКАТОРом приложения SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="42f64-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="42f64-644">Создание нового доверенного приложения для средства SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="42f64-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="42f64-645">Средство SEFAUTil можно запускать только на компьютере, входящем в пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="42f64-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="42f64-646">При необходимости Добавление пула в качестве нового доверенного пула приложений можно выполнить с помощью командной консоли Skype для бизнеса Server с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="42f64-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="42f64-647">UCMA 3,0 должен быть установлен на компьютере, который будет использоваться для запуска средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="42f64-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="42f64-648">Доверенное приложение должно быть определено в топологии для средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="42f64-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="42f64-649">Чтобы определить SEFAUtil как новое доверенное приложение, используйте командную консоль Skype для бизнеса Server и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="42f64-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="42f64-650">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="42f64-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="42f64-651">Полное доменное имя пула: полное доменное имя сервера или пула, на котором будет размещаться приложение SEFAUtil (обычно это сервер переднего плана Skype для бизнеса > или пул).</span><span class="sxs-lookup"><span data-stu-id="42f64-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="42f64-652">Полное доменное имя регистратора пула: полное доменное имя сервера или пула приложений Skype для бизнеса, связанных с этим пулом приложений.</span><span class="sxs-lookup"><span data-stu-id="42f64-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="42f64-653">Сайт пула: идентификатор сайта, на котором размещен этот пул.</span><span class="sxs-lookup"><span data-stu-id="42f64-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="42f64-654">Необходимо включить изменения топологии.</span><span class="sxs-lookup"><span data-stu-id="42f64-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="42f64-655">Включение изменений топологии можно выполнить с помощью командной консоли Skype для бизнеса Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="42f64-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="42f64-656">При необходимости установите средства набора ресурсов Skype для бизнеса Server 2015 на сервер, который будет использоваться для запуска средства SEFAUtil (сервер должен быть частью пула доверенных приложений).</span><span class="sxs-lookup"><span data-stu-id="42f64-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="42f64-657">Убедитесь, что SEFAUtil работает правильно.</span><span class="sxs-lookup"><span data-stu-id="42f64-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="42f64-658">Для этого запустите средство из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="42f64-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="42f64-659">По умолчанию средство будет размещено в: ". ..\Програм Files\Skype for Business Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="42f64-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="42f64-660">Чтобы отобразить параметры переадресации звонков для пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42f64-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="42f64-661">Должны отобразиться параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="42f64-662">Групповая отправка звонков</span><span class="sxs-lookup"><span data-stu-id="42f64-662">Group Call Pickup</span></span>

<span data-ttu-id="42f64-663">Для групповой отправки звонков требуется дополнительная настройка в Skype для бизнеса Server 2015, чтобы обеспечить возможность полной активации.</span><span class="sxs-lookup"><span data-stu-id="42f64-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="42f64-664">Перед назначением групп раскладки пользователям обратитесь к документации по продукту, чтобы получить сведения о планировании и развертывании этой возможности.</span><span class="sxs-lookup"><span data-stu-id="42f64-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-665">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="42f64-666">Отображение текущих параметров обработки звонков</span><span class="sxs-lookup"><span data-stu-id="42f64-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="42f64-667">Следующая команда отображает обработку вызовов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="42f64-668">В этом примере параметр **/Server** используется для задания подключения к Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="42f64-669">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="42f64-670">Установка назначения "переадресация вызовов/нет ответа"</span><span class="sxs-lookup"><span data-stu-id="42f64-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="42f64-671">В этом примере задается назначение ответа "перенаправление вызова", "нет ответа" и "Задержка звонка".</span><span class="sxs-lookup"><span data-stu-id="42f64-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="42f64-672">В этом случае параметр/Server не предоставляется; SEFAUtil пытается выполнить автообнаружение Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="42f64-673">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="42f64-674">Немедленное включение переадресации вызовов</span><span class="sxs-lookup"><span data-stu-id="42f64-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="42f64-675">В этом примере сразу же включается переадресация звонков для другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="42f64-676">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="42f64-677">Немедленное отключение переадресации вызовов</span><span class="sxs-lookup"><span data-stu-id="42f64-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="42f64-678">В этом примере немедленно отключается переадресация вызовов.</span><span class="sxs-lookup"><span data-stu-id="42f64-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="42f64-679">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="42f64-680">Добавление пользователя в качестве делегата и настройка одновременных звонков делегатов</span><span class="sxs-lookup"><span data-stu-id="42f64-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="42f64-681">В этом примере пользователь добавляется в качестве делегата и настраивает Одновременный звонок делегатов.</span><span class="sxs-lookup"><span data-stu-id="42f64-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="42f64-682">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="42f64-683">Изменение правила одновременных звонков делегатов</span><span class="sxs-lookup"><span data-stu-id="42f64-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="42f64-684">В этом примере изменяется правило одновременных звонков, которое было задано в предыдущем примере, в правило задержанных звонков.</span><span class="sxs-lookup"><span data-stu-id="42f64-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="42f64-685">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="42f64-686">Удаление делегата</span><span class="sxs-lookup"><span data-stu-id="42f64-686">Remove the Delegate</span></span>

<span data-ttu-id="42f64-687">В этом примере удаляется делегат.</span><span class="sxs-lookup"><span data-stu-id="42f64-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="42f64-688">При удалении последнего делегата делегат автоматически отключается.</span><span class="sxs-lookup"><span data-stu-id="42f64-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="42f64-689">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="42f64-690">Добавление делегата и настройка правила перенаправления звонка на "делегировать"</span><span class="sxs-lookup"><span data-stu-id="42f64-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="42f64-691">В этом примере добавляется делегат и настраивается правило перенаправления звонка на делегаты.</span><span class="sxs-lookup"><span data-stu-id="42f64-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="42f64-692">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="42f64-693">Включение одновременных звонков и задание номера назначения</span><span class="sxs-lookup"><span data-stu-id="42f64-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="42f64-694">В этом примере включается Одновременный звонок и задается номер назначения для одновременного звонка.</span><span class="sxs-lookup"><span data-stu-id="42f64-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="42f64-695">Чтобы изменить номер назначения одновременного звонка для пользователя, для которого уже включен Одновременный звонок, оставьте команду с параметром/енаблесимулринг, в противном случае целевой номер не изменится.</span><span class="sxs-lookup"><span data-stu-id="42f64-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="42f64-696">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="42f64-697">Отключение одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="42f64-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="42f64-698">В этом примере отключается Одновременный звонок.</span><span class="sxs-lookup"><span data-stu-id="42f64-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="42f64-699">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="42f64-700">Добавление члена группы для вызова команды и настройка одновременных звонков в группу участников группового звонка</span><span class="sxs-lookup"><span data-stu-id="42f64-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="42f64-701">В этом примере участник группы добавляется в группу звонков пользователя и включает одновременный Звонок группе звонков группы.</span><span class="sxs-lookup"><span data-stu-id="42f64-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="42f64-702">При добавлении участника в группу звонков для пользователя автоматически переключается Одновременный звонок сеттигс пользователей на выполнение его группу звонков в группу.</span><span class="sxs-lookup"><span data-stu-id="42f64-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="42f64-703">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="42f64-704">Удаление участника из группы звонков группы</span><span class="sxs-lookup"><span data-stu-id="42f64-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="42f64-705">В этом примере удаляется участник команды группы звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="42f64-706">Если удаляемый член является единственным участником группы звонков группы, одновременно звонить группе звонков группы будет автоматически отключено.</span><span class="sxs-lookup"><span data-stu-id="42f64-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="42f64-707">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="42f64-708">Установка отложенного звонка для группы звонков группы</span><span class="sxs-lookup"><span data-stu-id="42f64-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="42f64-709">В этом примере показано, как изменить параметр времени в группе звонков группы звонков.</span><span class="sxs-lookup"><span data-stu-id="42f64-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="42f64-710">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="42f64-711">Включение командного звонка</span><span class="sxs-lookup"><span data-stu-id="42f64-711">Enable Team-Call</span></span>

<span data-ttu-id="42f64-712">В этом примере включается групповой звонок для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="42f64-713">Если группа вызовов пользователя не имеет участников, вызов по команде не будет включен.</span><span class="sxs-lookup"><span data-stu-id="42f64-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="42f64-714">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="42f64-715">Отключение командного звонка</span><span class="sxs-lookup"><span data-stu-id="42f64-715">Disable Team-Call</span></span>

<span data-ttu-id="42f64-716">В этом примере отключается вызов по команде для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="42f64-717">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="42f64-718">Включение групповой отправки звонков и назначение группы раскладки пользователю</span><span class="sxs-lookup"><span data-stu-id="42f64-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="42f64-719">В этом примере группа раскладки назначается пользователю и включается запрос группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="42f64-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="42f64-720">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="42f64-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="42f64-721">Отключение отправки группового звонка</span><span class="sxs-lookup"><span data-stu-id="42f64-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="42f64-722">В этом примере отключается отправка группового звонка для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="42f64-723">При отключении групповой отправки звонков для пользователя номер группы, назначенный пользователю, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="42f64-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="42f64-724">Если вы попытаетесь повторно включить запрос групп для этого пользователя, необходимо повторно назначить номер группы с помощью параметра/енаблеграуппиккуп.</span><span class="sxs-lookup"><span data-stu-id="42f64-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="42f64-725">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="42f64-725">SYSPrep.ps1</span></span>
<span data-ttu-id="42f64-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="42f64-727">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-727">Description</span></span>

<span data-ttu-id="42f64-728">SYSPrep. ps1 — это сценарий Windows PowerShell, который будет устанавливать следующие необходимые компоненты Skype для бизнеса Server 2015 на компьютер с операционной системой Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="42f64-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="42f64-729">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="42f64-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="42f64-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="42f64-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="42f64-731">Windows PowerShell версии 3,0</span><span class="sxs-lookup"><span data-stu-id="42f64-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="42f64-732">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="42f64-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="42f64-733">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="42f64-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="42f64-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="42f64-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="42f64-735">Основные файлы Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="42f64-736">Имя скрипта аналогично средству подготовки системы для операционных систем Microsoft Windows, но они отличаются.</span><span class="sxs-lookup"><span data-stu-id="42f64-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="42f64-737">Этот сценарий установит необходимые компоненты для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="42f64-738">После установки необходимых компонентов средство SYSPrep можно использовать для создания образа сервера.</span><span class="sxs-lookup"><span data-stu-id="42f64-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-739">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-739">Requirements</span></span>

<span data-ttu-id="42f64-740">Перед выполнением сценария SYSPrep. ps1 необходимо скопировать файлы необходимых компонентов в локальную папку на компьютере с операционной системой Windows Server 2008 (например, **д:\сетуп)**.</span><span class="sxs-lookup"><span data-stu-id="42f64-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="42f64-741">В эту папку также необходимо включить копию файлов Skype для бизнеса Server 2015, в частности файл **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="42f64-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="42f64-742">Файлы необходимых компонентов можно скачать из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="42f64-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="42f64-743">**Необходимого**</span><span class="sxs-lookup"><span data-stu-id="42f64-743">**Prerequisite**</span></span>                                | <span data-ttu-id="42f64-744">**Location**</span><span class="sxs-lookup"><span data-stu-id="42f64-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="42f64-745">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="42f64-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="42f64-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="42f64-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="42f64-747">Windows PowerShell версии 3,0</span><span class="sxs-lookup"><span data-stu-id="42f64-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="42f64-748">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="42f64-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="42f64-749">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="42f64-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="42f64-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="42f64-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="42f64-751">Skype для бизнеса Server 2015 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="42f64-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="42f64-752">Копирование с носителя Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="42f64-753">Параметр</span><span class="sxs-lookup"><span data-stu-id="42f64-753">Parameter</span></span>

<span data-ttu-id="42f64-754">Параметр **– сетупфолдер** принимает в качестве аргумента расположение каталога необходимых файлов</span><span class="sxs-lookup"><span data-stu-id="42f64-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-755">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-755">Examples</span></span>

<span data-ttu-id="42f64-756">Чтобы запустить сценарий SYSPrep. ps1 и установить необходимые компоненты для Skype для бизнеса Server 2015, выполните следующую команду из командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="42f64-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="42f64-757">Миграция объявлений неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="42f64-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="42f64-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="42f64-759">Средство миграции оповещений о неназначенных номерах позволяет администратору Skype для бизнеса Server 2015 перенести конфигурацию неназначенных номеров, обслуживаемую приложением-оповещением с исходного сервера Skype для бизнеса Server или из пула в Целевой сервер или пул Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="42f64-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-760">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-760">Description</span></span>

<span data-ttu-id="42f64-761">Средство миграции объявлений неназначенных номеров — это сценарий Windows PowerShell, который перемещает конфигурацию неназначенных номеров, обслуживаемую приложением-объявлением исходного сервера или пула, на другой сервер или в пул.</span><span class="sxs-lookup"><span data-stu-id="42f64-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="42f64-762">При выполнении сценарий миграции неназначенных номеров будет выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="42f64-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="42f64-763">Переместите все звуковые файлы, используемые объявлениями неназначенных номеров приложения, размещенного на исходном сервере или в хранилище файлов на целевом сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42f64-764">Звуковые файлы удаляются из исходного пула после их копирования в конечный пул.</span><span class="sxs-lookup"><span data-stu-id="42f64-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="42f64-765">Переместите все объявления неназначенных номеров, настроенные для приложения для оповещений, размещенного на исходном сервере или в пуле, на целевом сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="42f64-766">Переназначение всех диапазонов неназначенных номеров, обслуживаемых приложением для извещения, размещенным на исходном сервере или в пуле, на конечный сервер или в пул.</span><span class="sxs-lookup"><span data-stu-id="42f64-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="42f64-767">После успешного выполнения сценария все диапазоны неназначенных номеров, Обслуживаемые приложением, размещенным на исходном сервере или в пуле, теперь будут обслуживаться с одинаковой конфигурацией на целевом сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="42f64-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-768">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-768">Output</span></span>

<span data-ttu-id="42f64-769">Сценарий **Move-CsAnnouncementConfiguration** указывает в окне командной консоли Skype для бизнеса Server, откуда она выполняла успешную или неудачную операцию миграции.</span><span class="sxs-lookup"><span data-stu-id="42f64-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="42f64-770">Если выполнение операции прерывается из-за любой ошибки, диапазоны неназначенных номеров, которые были успешно перемещены в назначение, останутся в месте назначения в рабочей форме, а остальные диапазоны неназначенных номеров для переноса останутся в Источник, а также Рабочая форма.</span><span class="sxs-lookup"><span data-stu-id="42f64-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="42f64-771">Чтобы полностью перенести оставшуюся часть конфигурации, повторно запустите сценарий после устранения ошибки.</span><span class="sxs-lookup"><span data-stu-id="42f64-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="42f64-772">Назначение</span><span class="sxs-lookup"><span data-stu-id="42f64-772">Purpose</span></span>

<span data-ttu-id="42f64-773">Сценарий переноса оповещений о неназначенных номерах можно использовать в следующих трех сценариях:</span><span class="sxs-lookup"><span data-stu-id="42f64-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="42f64-774">**Перенос параметров конфигурации в новую версию Skype для бизнеса Server:** Компания Contoso находится в процессе перехода на Skype для бизнеса Server 2015 и в процессе миграции администратор Skype для бизнеса Server хотел бы переместить конфигурацию неназначенных номеров, обслуживаемую приложением-оповещением, из развертывания Lync Server 2013 в новое развертывание Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="42f64-775">Чтобы переместить параметры конфигурации, администратор Skype для бизнеса Server использует средство миграции объявлений о неназначенных номерах.</span><span class="sxs-lookup"><span data-stu-id="42f64-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="42f64-776">**Откат развертывания с Skype для бизнеса server 2015 до Lync Server 2013:** Из-за непредвиденных факторов компания Contoso должна откатить миграцию на новое развертывание Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="42f64-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="42f64-777">Чтобы свести к минимуму перерывы в работе службы, администратор Skype для бизнеса Server использует средство миграции объявлений о неназначенных номерах для отката конфигурации из развертывания Skype для бизнеса Server 2015 к развертыванию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42f64-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="42f64-778">**Перемещение данных между развертываниями:** Компания Contoso находится в процессе замены всех серверов в одном пуле на новые серверы.</span><span class="sxs-lookup"><span data-stu-id="42f64-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="42f64-779">Их стратегия заключается в развертывании нового пула Skype для бизнеса Server 2015, перемещении всех данных из старой версии в новый пул, а затем использование старого пула.</span><span class="sxs-lookup"><span data-stu-id="42f64-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="42f64-780">После развертывания нового пула средство миграции объявлений неназначенных номеров используется для перемещения конфигурации из старого пула в новый.</span><span class="sxs-lookup"><span data-stu-id="42f64-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="42f64-781">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-781">Requirements</span></span>

<span data-ttu-id="42f64-782">Ниже приведены основные требования, необходимые для успешного запуска средства.</span><span class="sxs-lookup"><span data-stu-id="42f64-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="42f64-783">Сценарий необходимо запускать на компьютере с установленной консолью управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="42f64-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="42f64-784">Приложение объявления должно быть успешно развернуто на серверах или в пулах, использующих исходный и конечный Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="42f64-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="42f64-785">Сценарий Move – CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="42f64-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="42f64-786">Для скрипта Move – CsAnnouncementConfiguration требуются два параметра, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="42f64-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Параметры Move – CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="42f64-788">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="42f64-789">Перемещение конфигурации объявлений неназначенных номеров из пула Lync Server 2013 в пул Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="42f64-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="42f64-790">В этом примере показано перемещение объявлений неназначенных номеров из исходного пула (Lync Server 2013) в целевой пул (Skype для бизнеса Server 2015).</span><span class="sxs-lookup"><span data-stu-id="42f64-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="42f64-791">Перемещение конфигурации объявлений неназначенных номеров из пула Skype для бизнеса Server 2015 в пул Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42f64-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="42f64-792">В этом примере показано перемещение объявлений неназначенных номеров из исходного пула (Skype для бизнеса Server 2015) в целевой пул (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="42f64-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="42f64-793">Данные Web CONF</span><span class="sxs-lookup"><span data-stu-id="42f64-793">Web Conf Data</span></span>
<span data-ttu-id="42f64-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="42f64-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="42f64-795">Средство Web CONF Data позволяет администратору программного обеспечения для обмена мгновенными сообщениями Skype для бизнеса Server 2015 получить более полный контроль над данными, связанными с веб-конференциями организатора.</span><span class="sxs-lookup"><span data-stu-id="42f64-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="42f64-796">Сценарии включают возможность удалять данные о собрании определенного пользователя на основе условий штампа времени.</span><span class="sxs-lookup"><span data-stu-id="42f64-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="42f64-797">Описание</span><span class="sxs-lookup"><span data-stu-id="42f64-797">Description</span></span>

<span data-ttu-id="42f64-798">Это средство позволяет администратору выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="42f64-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="42f64-799">Поиск всех данных веб-конференций, связанных с одним пользователем.</span><span class="sxs-lookup"><span data-stu-id="42f64-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="42f64-800">Удалить все данные веб-конференций, связанные с отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="42f64-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="42f64-801">Удалить все данные веб-конференций, связанные с одним пользователем старше определенной даты.</span><span class="sxs-lookup"><span data-stu-id="42f64-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="42f64-802">Переместить все данные веб-конференций, связанные с отдельным пользователем, когда пользователь перемещается из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="42f64-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="42f64-803">Средства набора ресурсов для Lync Server 2010 поддерживают перемещение всех данных веб-конференций, связанных с одним пользователем, когда пользователь перемещается из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="42f64-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="42f64-804">Эта функция теперь нерекомендуема для этого средства в пользу параметра **мовеконференцедата** .</span><span class="sxs-lookup"><span data-stu-id="42f64-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="42f64-805">Для получения дополнительных сведений об этом параметре обратитесь к командлету [Move – CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="42f64-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="42f64-806">Средство удаляет данные собраний только для неактивных собраний.</span><span class="sxs-lookup"><span data-stu-id="42f64-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="42f64-807">Невозможно удалить активные собрания (или собрания в сеансах).</span><span class="sxs-lookup"><span data-stu-id="42f64-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="42f64-808">Это средство необходимо запускать на компьютере, который находится в том же пуле, что и целевой пользователь.</span><span class="sxs-lookup"><span data-stu-id="42f64-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="42f64-809">Пользователи, чьи данные контента собраний управляются этим средством, должны находиться в том же пуле пользователей.</span><span class="sxs-lookup"><span data-stu-id="42f64-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="42f64-810">Output</span><span class="sxs-lookup"><span data-stu-id="42f64-810">Output</span></span>

<span data-ttu-id="42f64-811">Это средство выводит результаты каждой из операций:</span><span class="sxs-lookup"><span data-stu-id="42f64-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="42f64-812">Если выполняется запрос, средство выводит список всех неактивных папок с данными собраний, в которых этот пользователь является организатором.</span><span class="sxs-lookup"><span data-stu-id="42f64-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="42f64-813">Если выполняется удаление, средство выводит список всех папок с данными собраний, чьи данные будут удалены.</span><span class="sxs-lookup"><span data-stu-id="42f64-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="42f64-814">Requirements</span><span class="sxs-lookup"><span data-stu-id="42f64-814">Requirements</span></span>

<span data-ttu-id="42f64-815">Средство должно быть запущено в том же пуле, в котором в данный момент размещен Организатор.</span><span class="sxs-lookup"><span data-stu-id="42f64-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="42f64-816">Средство необходимо запускать с правами администратора с доступом к хранилищу файлов контента.</span><span class="sxs-lookup"><span data-stu-id="42f64-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="42f64-817">Примеры</span><span class="sxs-lookup"><span data-stu-id="42f64-817">Examples</span></span>

<span data-ttu-id="42f64-818">В следующей таблице описываются параметры, некоторые из которых используются в примерах.</span><span class="sxs-lookup"><span data-stu-id="42f64-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Параметры Web CONF Data Tool.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="42f64-820">В предыдущем примере показано, как работает команда запроса.</span><span class="sxs-lookup"><span data-stu-id="42f64-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="42f64-821">Результатом такой команды будет список всех папок контента собраний, которые будут затронуты этим средством.</span><span class="sxs-lookup"><span data-stu-id="42f64-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="42f64-822">Предыдущий пример команды DELETE.</span><span class="sxs-lookup"><span data-stu-id="42f64-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="42f64-823">Команда Delete удалит все неактивные папки собраний от этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="42f64-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="42f64-824">Сводка</span><span class="sxs-lookup"><span data-stu-id="42f64-824">Summary</span></span>

<span data-ttu-id="42f64-825">Это средство может быть ценным ресурсом для администраторов, которым необходим более точный контроль над данными для собраний по конференциям.</span><span class="sxs-lookup"><span data-stu-id="42f64-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>


