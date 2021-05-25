---
title: Skype для бизнеса Server 2015 Документация по набору ресурсов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: В этой статье описываются средства в наборе ресурсов Skype для бизнеса Server 2015 г., включая назначение каждого средства, а также примеры его использования. Набор ресурсов Skype для бизнеса Server 2015 г. помогает упростить выполнение рутинных задач для ИТ-администраторов, развертывавших и Skype для бизнеса Server 2015 г. Например, средство Web Conf Data можно использовать для легкого управления данными, которые загружаются пользователями во время собрания в Интернете. Средство SEFAUtil можно использовать для создания переадэстройки и ответа на вызовы делегатов для пользователей. Мы рекомендуем ИТ-администраторам использовать эти средства для более эффективного управления Skype для бизнеса Server 2015 г.
ms.openlocfilehash: 6c68a94d331f2ad5f9ffaa169228aa9d64e41293
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629048"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="216b9-107">Skype для бизнеса Server 2015 Документация по набору ресурсов</span><span class="sxs-lookup"><span data-stu-id="216b9-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="216b9-108">В этой статье описываются средства в наборе ресурсов Skype для бизнеса Server 2015 г., включая назначение каждого средства, а также примеры его использования.</span><span class="sxs-lookup"><span data-stu-id="216b9-108">This article describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="216b9-109">Набор ресурсов Skype для бизнеса Server 2015 г. помогает упростить выполнение рутинных задач для ИТ-администраторов, развертывавших и Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="216b9-110">Например, средство **Web Conf Data** можно использовать для легкого управления данными, которые загружаются пользователями во время собрания в Интернете.</span><span class="sxs-lookup"><span data-stu-id="216b9-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="216b9-111">Средство **SEFAUtil** можно использовать для создания переадэстройки и ответа на вызовы делегатов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="216b9-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="216b9-112">Мы рекомендуем ИТ-администраторам использовать эти средства для более эффективного управления Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="216b9-113">Установка средств набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="216b9-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="216b9-114">Чтобы установить набор ресурсов Skype для бизнеса Server 2015 г., [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) из Центра загрузки.</span><span class="sxs-lookup"><span data-stu-id="216b9-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="216b9-115">Запустите **OCSResKit.msi,** чтобы выполнить простую установку.</span><span class="sxs-lookup"><span data-stu-id="216b9-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="216b9-116">В .msi устанавливаются все средства по следующему пути: **%Program Files%\Skype для бизнеса Server 2015\ResKit**.</span><span class="sxs-lookup"><span data-stu-id="216b9-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="216b9-117">Средства, которые являются автономными исполняемыми, находятся в этой папке.</span><span class="sxs-lookup"><span data-stu-id="216b9-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="216b9-118">Средства, которые также имеют вспомогательные файлы, находятся в своих подмостках.</span><span class="sxs-lookup"><span data-stu-id="216b9-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="216b9-119">Поддерживаемые среды</span><span class="sxs-lookup"><span data-stu-id="216b9-119">Supported Environments</span></span>

<span data-ttu-id="216b9-120">Набор ресурсов Skype для бизнеса Server 2015 года должен быть установлен на сервере, который соответствует требованиям, требуемой для Skype для бизнеса Server 2015 г., обычно для Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="216b9-121">Обзор средств набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="216b9-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="216b9-122">Ниже представлен список средств, предоставляемых в наборе ресурсов Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="216b9-123">Описание каждого средства, включая требования и пример использования, описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="216b9-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="216b9-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="216b9-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="216b9-125">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="216b9-126">Анализатор использования пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="216b9-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="216b9-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="216b9-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="216b9-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="216b9-129">Импорт служба хранилища данных службы</span><span class="sxs-lookup"><span data-stu-id="216b9-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="216b9-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="216b9-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="216b9-131">Консоль пользователя Lookup</span><span class="sxs-lookup"><span data-stu-id="216b9-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="216b9-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="216b9-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="216b9-133">Просмотр конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="216b9-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="216b9-134">Агент группы ответов в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="216b9-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="216b9-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="216b9-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="216b9-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="216b9-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="216b9-137">Миграция неназвных объявлений номеров</span><span class="sxs-lookup"><span data-stu-id="216b9-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="216b9-138">Данные веб-конфи</span><span class="sxs-lookup"><span data-stu-id="216b9-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="216b9-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="216b9-139">ABSConfig</span></span>
<span data-ttu-id="216b9-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="216b9-141">Средство конфигурации служб адресной книги (ABSConfig) — это административный инструмент, который помогает администраторам настраивать конфигурацию службы адресных книг в Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="216b9-142">Этот инструмент также позволяет Skype для бизнеса Server 2015 года для восстановления параметров службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="216b9-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-143">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-143">Description</span></span>

<span data-ttu-id="216b9-144">ABSConfig — это графическое приложение пользовательского интерфейса, которое позволяет администраторам настраивать атрибуты служб домена Active Directory, связанные со службой адресной книги.</span><span class="sxs-lookup"><span data-stu-id="216b9-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="216b9-145">Основные сценарии для этого средства:</span><span class="sxs-lookup"><span data-stu-id="216b9-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="216b9-146">Чтобы администраторы могли соединить атрибуты служб домена Active Directory с атрибутами для Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="216b9-147">Чтобы администраторы могли указать атрибут Службы домена Active Directory, который должен быть включен или исключен в файлы службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="216b9-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="216b9-148">Чтобы администраторы могли восстановить параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="216b9-148">To enable administrators to restore,  default Address Book Service settings.</span></span>

<span data-ttu-id="216b9-149">Инструмент ABSConfig можно начать с помощью ABSConfig.exe файла.</span><span class="sxs-lookup"><span data-stu-id="216b9-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="216b9-150">Средство открывает вкладку **Configure Attributes.** В этой таблице можно соединить атрибуты служб домена Active Directory с полями атрибутов за Skype для бизнеса Server 2015 г. и указать, какие пользователи должны включать или исключать в файлы службы адресных книг на основе определенных фильтров атрибутов.</span><span class="sxs-lookup"><span data-stu-id="216b9-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="216b9-151">Он также имеет параметры для настройки значения номера телефона, который будет включен в файл адресной книги.</span><span class="sxs-lookup"><span data-stu-id="216b9-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="216b9-152">Параметр **Restore Defaults** позволяет администраторам восстанавливать параметры службы адресных книг до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="216b9-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="216b9-153">Повторное сопоставление атрибутов AD с различными именами полей OC будет работать только для загрузки файлов адресной книги и не поддерживается веб-запросом адресной книги.</span><span class="sxs-lookup"><span data-stu-id="216b9-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-154">Output</span></span>

<span data-ttu-id="216b9-155">ABSConfig хранит конфигурацию службы адресных книг в базе данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="216b9-156">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-156">Purpose</span></span>

<span data-ttu-id="216b9-157">ABSConfig предоставляет быстрый и простой способ настройки службы адресной книги 2015 Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-158">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="216b9-159">Компьютер</span><span class="sxs-lookup"><span data-stu-id="216b9-159">Computer</span></span>

<span data-ttu-id="216b9-160">ABSConfig можно запускать только с компьютера, подключитого к домену, Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="216b9-161">В случае Skype для бизнеса Server 2015 г. выпуск Enterprise этот инструмент можно запустить на Front-End серверах, на которые включена служба адресной книги во время установки.</span><span class="sxs-lookup"><span data-stu-id="216b9-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front-End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="216b9-162">Сеть</span><span class="sxs-lookup"><span data-stu-id="216b9-162">Network</span></span>

<span data-ttu-id="216b9-163">Компьютер должен иметь возможность подключаться к Front-End пулу и задней базе данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-163">The computer should be able to connect to the Front-End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="216b9-164">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="216b9-164">Software</span></span>

<span data-ttu-id="216b9-165">Перед запуском инструмента ABSConfig необходимо установить следующие компоненты программного обеспечения:</span><span class="sxs-lookup"><span data-stu-id="216b9-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="216b9-166">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="216b9-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="216b9-167">Пользователи</span><span class="sxs-lookup"><span data-stu-id="216b9-167">Users</span></span>

<span data-ttu-id="216b9-168">Администраторы, у которых есть разрешения, необходимые для обновления Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-169">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-169">Examples</span></span>

<span data-ttu-id="216b9-170">ABSConfig можно начать с вводаABSConfig.exe **по** командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="216b9-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="216b9-171">Ниже показан пользовательский интерфейс инструмента ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="216b9-171">Shown below is the ABSConfig tool user interface.</span></span>

![Средство ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="216b9-173">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-173">Summary</span></span>

<span data-ttu-id="216b9-174">Средство ABSConfig предоставляет администраторам быстрый и простой в использовании инструмент для настройки службы адресных книг 2015 Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="216b9-175">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="216b9-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="216b9-177">Средство Мониторинга политики пропускной способности предназначено для того, чтобы администраторы просмотрели список следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="216b9-178">Все настроенные Skype для бизнеса Server 2015 службы политики пропускной способности (проверка подлинности и core) в топологии</span><span class="sxs-lookup"><span data-stu-id="216b9-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="216b9-179">Подключения каждой службы к другим службам политики пропускной способности и к серверам Edge</span><span class="sxs-lookup"><span data-stu-id="216b9-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="216b9-180">Все ссылки, настроенные в документе конфигурации сети и использовании пропускной способности в режиме реального времени, как сообщается каждой из служб политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="216b9-181">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-181">Description</span></span>

<span data-ttu-id="216b9-182">Средство Мониторинга политики пропускной способности реализуется в качестве приложения на основе GUI.</span><span class="sxs-lookup"><span data-stu-id="216b9-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="216b9-183">Администраторы запускают средство, запуская PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="216b9-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="216b9-184">Когда средство запускается, он пытается обнаружить список служб политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="216b9-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="216b9-185">После первоначального обновления области слева от окна заполняется список служб, которые сгруппируются по кластерам, которые они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="216b9-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="216b9-186">Когда администраторы выбирают определенную службу политики пропускной способности, на правой области отображаются сведения об этой конкретной службе.</span><span class="sxs-lookup"><span data-stu-id="216b9-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="216b9-187">На этой области также есть две основные вкладки, на которые отображаются сведения.</span><span class="sxs-lookup"><span data-stu-id="216b9-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="216b9-188">Вкладка Сведения о машине</span><span class="sxs-lookup"><span data-stu-id="216b9-188">Machine Info Tab</span></span>

<span data-ttu-id="216b9-189">На **вкладке** Machine Info показаны сведения о выбранной службе политики пропускной способности и списке и состоянии всех подключений, которые сделаны выбранной службой политики пропускной способности к другим службам.</span><span class="sxs-lookup"><span data-stu-id="216b9-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="216b9-190">Вкладка Топология Info</span><span class="sxs-lookup"><span data-stu-id="216b9-190">Topology Info Tab</span></span>

<span data-ttu-id="216b9-191">На **вкладке Топология Info** показан список всех ссылок, настроенных в параметрах конфигурации Сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="216b9-192">Для каждой ссылки отображается пропускная способность аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="216b9-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="216b9-193">Кроме того, отображается используемая в настоящее время пропускная способность как в Kbps, так и в процентах от емкости.</span><span class="sxs-lookup"><span data-stu-id="216b9-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="216b9-194">Средство использует цветовое кодирование, чтобы выделить ссылки с использованием, которые близки к емкости, что позволяет администраторам быстро изолировать такие ссылки.</span><span class="sxs-lookup"><span data-stu-id="216b9-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="216b9-195">Если средство Мониторинга политики пропускной способности испытывает сбой при подключении к какой-либо  из настроенных служб политики пропускной способности, сведения в машинной информации и вкладки **Топология Info** не будут заполнены.</span><span class="sxs-lookup"><span data-stu-id="216b9-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="216b9-196">Однако не исключено, что средство может подключиться изначально, но впоследствии потерять подключение к службе.</span><span class="sxs-lookup"><span data-stu-id="216b9-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="216b9-197">В таких случаях администраторы могут видеть устаревшие сведения.</span><span class="sxs-lookup"><span data-stu-id="216b9-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="216b9-198">На каждой **вкладке** имеется отметка последнего обновленного времени, которая позволяет администраторам видеть, когда данные были обновлены в последний раз для определенной службы политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="216b9-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-199">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-199">Output</span></span>

<span data-ttu-id="216b9-200">Выход командной строки не существует; выход программы содержится в основном графическом пользовательском интерфейсе (GUI).</span><span class="sxs-lookup"><span data-stu-id="216b9-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-201">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-201">Purpose</span></span>

<span data-ttu-id="216b9-202">Цель средства Мониторинга политики пропускной способности — разрешить администраторам видимость состояния каждой из служб политики пропускной способности, определенных в топологии.</span><span class="sxs-lookup"><span data-stu-id="216b9-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="216b9-203">Кроме того, администраторы могут видеть использование пропускной способности в режиме реального времени для всех ссылок, определенных в документе конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-204">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-204">Requirements</span></span>

<span data-ttu-id="216b9-205">Средство Мониторинга политики пропускной способности должно запускаться на компьютере, который является частью Skype для бизнеса Server топологии.</span><span class="sxs-lookup"><span data-stu-id="216b9-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="216b9-206">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-206">Summary</span></span>

<span data-ttu-id="216b9-207">Средство Мониторинга политики пропускной способности может быть ценным ресурсом для администраторов, чтобы они могли проверять состояние всех служб политики пропускной способности в топологии, и что еще более важно— они могут получать использование пропускной способности в режиме реального времени для ссылок, определенных в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="216b9-208">Анализатор использования пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="216b9-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-209"><a name="bua"> </a></span></span>

<span data-ttu-id="216b9-210">Анализатор использования пропускной способности — это средство, которое создает отчеты о различных представлениях потребления пропускной способности конечными точками UC по ссылкам WAN в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="216b9-211">Эти отчеты можно использовать для понимания текущего шаблона потребления пропускной способности и для планирования пропускной способности пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="216b9-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-212">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-212">Description</span></span>

<span data-ttu-id="216b9-213">Анализатор использования пропускной способности реализуется в качестве приложения на основе GUI.</span><span class="sxs-lookup"><span data-stu-id="216b9-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="216b9-214">Этот инструмент создает отчеты специально для использования аудио в сети и помогает с планированием емкости.</span><span class="sxs-lookup"><span data-stu-id="216b9-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="216b9-215">Он также итерирует пропускную способность, назначенную различным ссылкам.</span><span class="sxs-lookup"><span data-stu-id="216b9-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-216">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-216">Output</span></span>

<span data-ttu-id="216b9-217">Анализатор использования пропускной способности предоставляет графические участки пропускной способности и использования для аудио для всех WAN-ссылок, настроенных в системе.</span><span class="sxs-lookup"><span data-stu-id="216b9-217">Bandwidth Utilization Analyzer provides graphical plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-218">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-218">Purpose</span></span>

<span data-ttu-id="216b9-219">В любом развертывании голосовых и видеосвязи важно отслеживать и понимать тенденцию использования пропускной способности трафика мультимедиа в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="216b9-220">Средство анализатора использования пропускной способности позволяет администратору достичь именно этого.</span><span class="sxs-lookup"><span data-stu-id="216b9-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="216b9-221">Этот инструмент делает следующее:</span><span class="sxs-lookup"><span data-stu-id="216b9-221">This tool does the following:</span></span>

- <span data-ttu-id="216b9-222">Создает конкретные отчеты для использования аудио в сети</span><span class="sxs-lookup"><span data-stu-id="216b9-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="216b9-223">Помогает более эффективному планированию емкости и итерации пропускной способности, которая назначена различным ссылкам</span><span class="sxs-lookup"><span data-stu-id="216b9-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="216b9-224">Анализатор использования пропускной способности может создавать графические участки отчетов о пропускной способности и использовании; они являются следующими:</span><span class="sxs-lookup"><span data-stu-id="216b9-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="216b9-225">Все ссылки WAN в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="216b9-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="216b9-226">Фильтруемая выбранными ссылками WAN</span><span class="sxs-lookup"><span data-stu-id="216b9-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="216b9-227">Фильтрация по ссылкам WAN с превышением емкости ссылок</span><span class="sxs-lookup"><span data-stu-id="216b9-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="216b9-228">Фильтруются ссылки WAN, которые недополучит предусмотренную полосу пропускания</span><span class="sxs-lookup"><span data-stu-id="216b9-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="216b9-229">Фильтр по ссылкам WAN, достигающим критических уровней (использование пропускной способности, которое превышает 90% пропускной способности WAN-ссылки)</span><span class="sxs-lookup"><span data-stu-id="216b9-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="216b9-230">Фильтруется по типу ссылки WAN-network-site, межрегиональным ссылкам и ссылкам на сайте</span><span class="sxs-lookup"><span data-stu-id="216b9-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="216b9-231">Фильтрация по сетевому региону</span><span class="sxs-lookup"><span data-stu-id="216b9-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="216b9-232">Приложения</span><span class="sxs-lookup"><span data-stu-id="216b9-232">Applications</span></span>

<span data-ttu-id="216b9-233">Анализатор использования пропускной способности имеет следующие два приложения (средства):</span><span class="sxs-lookup"><span data-stu-id="216b9-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="216b9-234">**WanLinkLogCollector.exe** Этот инструмент позволяет пользователю вводить требуемую информацию.</span><span class="sxs-lookup"><span data-stu-id="216b9-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="216b9-235">**BandwidthUtilizationAnalyzer.xlsm** Отчет Microsoft Excel таблицы автоматически запущен WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="216b9-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="216b9-236">Это приложение позволяет пользователю применять фильтры к отчету, как показано ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="216b9-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="216b9-237">Этапы использования анализатора использования пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="216b9-238">При использовании анализатора использования пропускной способности существует два этапа:</span><span class="sxs-lookup"><span data-stu-id="216b9-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="216b9-239">Сбор журналов, выполняемых с помощью WanLinkLogCollector.exe</span><span class="sxs-lookup"><span data-stu-id="216b9-239">Collect logs, which are performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="216b9-240">Настройка отчетов, выполняемых с помощью BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="216b9-240">Customize reports, which are performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="216b9-241">Мы настоятельно рекомендуем BandwidthUtilizationAnalyzer.xlsне запускать м вручную конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="216b9-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="216b9-242">Запуск анализатора использования пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="216b9-243">Начните WanLinkLogCollector.exe в командной подсказке или с помощью Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="216b9-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="216b9-244">**Использование WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="216b9-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="216b9-245">Существует три шага к использованию WanLinkLogCollector.exe:</span><span class="sxs-lookup"><span data-stu-id="216b9-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="216b9-246">**Журнал временной шкалы** Укай сроки, которые необходимо сгенерить для отчета</span><span class="sxs-lookup"><span data-stu-id="216b9-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="216b9-247">**Укажите каталоги файлов** Предоставление сведений о расположении файлов</span><span class="sxs-lookup"><span data-stu-id="216b9-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="216b9-248">**Сбор журналов и запуск просмотра отчетов** Выполните команду для создания отчета</span><span class="sxs-lookup"><span data-stu-id="216b9-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="216b9-249">Шаг 1 . Журнал временной шкалы</span><span class="sxs-lookup"><span data-stu-id="216b9-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="216b9-250">Ведение журнала временной шкалы позволяет пользователю средства указать следующее, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="216b9-251">**Дата начала** Это дата начала хронологии, для которую должен быть создан отчет; например, 1 августа 2010 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="216b9-252">**Дата окончания** Это дата окончания временной шкалы, для которую должен быть создан отчет; например, 30 сентября 2010 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Даты начала и окончания использования пропускной способности A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="216b9-254">Шаг 2 . Укажите каталоги файлов</span><span class="sxs-lookup"><span data-stu-id="216b9-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="216b9-255">Указанные ниже каталоги файлов могут быть указаны пользователем показано.</span><span class="sxs-lookup"><span data-stu-id="216b9-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="216b9-256">**Расположение файлов журнала сервера** Расположение папки, где хранятся журналы серверов политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="216b9-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="216b9-257">Как правило, это<\<fileserver\> \\ fe \> \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="216b9-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="216b9-258">**Временное расположение хранилища файлов** Временное расположение файла, в котором хранятся промежуточные файлы во время сгенерации отчета.</span><span class="sxs-lookup"><span data-stu-id="216b9-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Каталоги файлов в anal использования пропускной способности](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="216b9-260">Убедитесь, что пользователю инструмента предоставляется достаточный доступ к журналам серверов и временной папке хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="216b9-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="216b9-261">Шаг 3 . Сбор журналов и запуск просмотра отчетов</span><span class="sxs-lookup"><span data-stu-id="216b9-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="216b9-262">Чтобы собрать журналы и запустить просмотр отчетов, нажмите **кнопку Выполнить,** как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="216b9-263">На этом этапе собираются необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="216b9-263">This step collects the required data.</span></span>

![Сбор данных в analy использования пропускной способности](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="216b9-265">После успешной проверки ввода отображается сообщение, показанное ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Журналы, собранные уведомления в Utili пропускной способности](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="216b9-267">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="216b9-267">Click **OK**.</span></span> <span data-ttu-id="216b9-268">BandwidthUtilizationAnalyzer.xlsм автоматически запущен.</span><span class="sxs-lookup"><span data-stu-id="216b9-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="216b9-269">Следуйте инструкциям в поле сообщений.</span><span class="sxs-lookup"><span data-stu-id="216b9-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="216b9-270">Подробные сведения см. **в BandwidthUtilizationAnalyzer.xlsm** в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="216b9-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="216b9-271">Использование BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="216b9-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="216b9-272">Когда BandwidthUtilizationAnalyzer.xlsм автоматически запущен, щелкните **Обновить,** как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="216b9-274">Когда папка файлов открывается, выберите consolidated.csv из расположения, указанного в поле сообщений, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="216b9-275">В нем также показано расположение **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="216b9-275">It also shows the location as **C:\Temp**.</span></span>

     ![Открытие папки в BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="216b9-277">Нажмите кнопку **Импортировать**.</span><span class="sxs-lookup"><span data-stu-id="216b9-277">Click **Import**.</span></span>

4. <span data-ttu-id="216b9-278">Графический сюжет создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="216b9-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="216b9-279">Он доступен при исчезновении указателя рабочей фоновой точки.</span><span class="sxs-lookup"><span data-stu-id="216b9-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Применение фильтров в представлении отчета.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="216b9-281">Применение фильтров к представлению отчета</span><span class="sxs-lookup"><span data-stu-id="216b9-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="216b9-282">Фильтры, которые можно применить к представлению отчета, как показано ниже, описаны следующим образом:</span><span class="sxs-lookup"><span data-stu-id="216b9-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Применение фильтров в представлении отчета.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="216b9-284">**Имя** Фильтр по ссылкам WAN (фильтр находится на правой стороне графика).</span><span class="sxs-lookup"><span data-stu-id="216b9-284">**Name** Filter by WAN links (the filter is on the right side of the graph).</span></span> <span data-ttu-id="216b9-285">Префикс обозначает следующие типы ссылок; см. вертикальное (синее) поле:</span><span class="sxs-lookup"><span data-stu-id="216b9-285">The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="216b9-286">**Сайт S** Ссылка WAN с сетевого сайта на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="216b9-286">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="216b9-287">**Is Inter-Site** Связь WAN между двумя сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="216b9-287">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="216b9-288">**R Межрегион** Связь WAN между двумя сетевыми регионами</span><span class="sxs-lookup"><span data-stu-id="216b9-288">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="216b9-289">**Превышение лимита** Фильтр по ссылкам WAN, использование пропускной способности которых превышает пропускную способность</span><span class="sxs-lookup"><span data-stu-id="216b9-289">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="216b9-290">**Критические уровни** Фильтр по ссылкам WAN, использование пропускной способности которых достигло 90% или больше пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-290">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="216b9-291">**Недоосвояемая** Фильтр по ссылкам WAN, использование пропускной способности которых составляет менее 25% пропускной способности</span><span class="sxs-lookup"><span data-stu-id="216b9-291">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="216b9-292">**Тип ссылки** Фильтр по следующим типам ссылок WAN:</span><span class="sxs-lookup"><span data-stu-id="216b9-292">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="216b9-293">**Тип сетевого** сайта</span><span class="sxs-lookup"><span data-stu-id="216b9-293">**Network site** type</span></span>

   - <span data-ttu-id="216b9-294">**Тип междометия**</span><span class="sxs-lookup"><span data-stu-id="216b9-294">**Inter-site** type</span></span>

   - <span data-ttu-id="216b9-295">**Тип ссылки между регионами**</span><span class="sxs-lookup"><span data-stu-id="216b9-295">**Inter-Region link** type</span></span>

6. <span data-ttu-id="216b9-296">**Регион** Фильтрация по сетевому региону</span><span class="sxs-lookup"><span data-stu-id="216b9-296">**Region** Filter by network region</span></span>

<span data-ttu-id="216b9-297">На следующих рисунках покажут описанные ранее фильтры.</span><span class="sxs-lookup"><span data-stu-id="216b9-297">The following figures show the previously described filters.</span></span>

<span data-ttu-id="216b9-298">Фильтр по **имени**.</span><span class="sxs-lookup"><span data-stu-id="216b9-298">Filter by **Name**.</span></span> <span data-ttu-id="216b9-299">Выберите список ссылок, которые необходимо отобразить на графике.</span><span class="sxs-lookup"><span data-stu-id="216b9-299">Select the list of links that need to be displayed in the graph.</span></span>

![Фильтрация по имени в bandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="216b9-301">Фильтр по **превышению лимита**.</span><span class="sxs-lookup"><span data-stu-id="216b9-301">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="216b9-302">Выберите **True,** чтобы обеспечить соблюдение фильтра.</span><span class="sxs-lookup"><span data-stu-id="216b9-302">Select **True** to enforce the filter.</span></span>

![Фильтрация по превышению лимита.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="216b9-304">Фильтр по **критическим уровням**.</span><span class="sxs-lookup"><span data-stu-id="216b9-304">Filter by **Critical levels**.</span></span> <span data-ttu-id="216b9-305">Выберите **True,** чтобы обеспечить соблюдение фильтра.</span><span class="sxs-lookup"><span data-stu-id="216b9-305">Select **True** to enforce the filter.</span></span>

![Фильтрация по критическим уровням.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="216b9-307">Фильтр по **under используется**.</span><span class="sxs-lookup"><span data-stu-id="216b9-307">Filter by **Under utilized**.</span></span> <span data-ttu-id="216b9-308">Выберите **True,** чтобы обеспечить соблюдение фильтра.</span><span class="sxs-lookup"><span data-stu-id="216b9-308">Select **True** to enforce the filter.</span></span>

![Фильтрация с помощью under Utilized.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="216b9-310">Фильтр по **типу link**.</span><span class="sxs-lookup"><span data-stu-id="216b9-310">Filter by **Link Type**.</span></span> <span data-ttu-id="216b9-311">Выберите тип или типы, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="216b9-311">Select the type or types that need to be displayed.</span></span>

![Фильтрация по типу link.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="216b9-313">Фильтр по **регионам**.</span><span class="sxs-lookup"><span data-stu-id="216b9-313">Filter by **Region**.</span></span> <span data-ttu-id="216b9-314">Выберите список регионов, ссылки которых необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="216b9-314">Select a list of regions whose links need to be displayed.</span></span>

![Фильтрация по региону.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="216b9-316">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-316">Requirements</span></span>

- <span data-ttu-id="216b9-317">The платформа .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="216b9-317">The .NET Framework 3.5</span></span>

- <span data-ttu-id="216b9-318">Microsoft Excel 2010, русская версия или Excel 2007 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-318">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="216b9-319">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-319">Summary</span></span>

<span data-ttu-id="216b9-320">Анализатор использования пропускной способности используется для сюжета использования звуковой пропускной способности для трафика UC по всей сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-320">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="216b9-321">Этот инструмент также можно использовать для сообщения об использовании пропускной способности видео в сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-321">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="216b9-322">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="216b9-322">Call Parkometer</span></span>
<span data-ttu-id="216b9-323"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-323"><a name="callpark"> </a></span></span>

<span data-ttu-id="216b9-324">Call Parkometer — это приложение командной строки, которое обеспечивает легкий доступ к базе данных орбиты Call Park.</span><span class="sxs-lookup"><span data-stu-id="216b9-324">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-325">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-325">Description</span></span>

<span data-ttu-id="216b9-326">Паркометр вызовов — это средство для отслеживания припаркованных вызовов.</span><span class="sxs-lookup"><span data-stu-id="216b9-326">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="216b9-327">Он также собирает статистику об орбитах и использовании Call Park Server (CPS).</span><span class="sxs-lookup"><span data-stu-id="216b9-327">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="216b9-328">Этот инструмент командной строки обеспечивает как чтение, так и доступ к SQL Server КПС с локального или удаленно подключенного компьютера.</span><span class="sxs-lookup"><span data-stu-id="216b9-328">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="216b9-329">Все параметры взаимоисключающие.</span><span class="sxs-lookup"><span data-stu-id="216b9-329">All options are mutually exclusive.</span></span> <span data-ttu-id="216b9-330">Синтаксис командной строки:</span><span class="sxs-lookup"><span data-stu-id="216b9-330">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="216b9-331">**-o** parameter — списки всех диапазонов орбит, настроенных для этого пула.</span><span class="sxs-lookup"><span data-stu-id="216b9-331">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="216b9-332">**-n** параметр — списки всех используемых в настоящее время орбит в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="216b9-332">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="216b9-333">Отображаемая информация будет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="216b9-333">The information displayed is as follows:</span></span>

  - <span data-ttu-id="216b9-334">Идентификатор единого ресурса SIP (URI) паркетника и паркера.</span><span class="sxs-lookup"><span data-stu-id="216b9-334">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="216b9-335">Имя хозяйского cpS, где вызов припаркован.</span><span class="sxs-lookup"><span data-stu-id="216b9-335">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="216b9-336">Отметка времени, когда вызов был припаркован.</span><span class="sxs-lookup"><span data-stu-id="216b9-336">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="216b9-337">**параметр -f—** перечисляет количество свободных в настоящее время орбит в пуле.</span><span class="sxs-lookup"><span data-stu-id="216b9-337">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="216b9-338">**-r \<n\>** параметр — списки \<n\> последних припаркованных вызовов.</span><span class="sxs-lookup"><span data-stu-id="216b9-338">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="216b9-339">Отображаемая информация будет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="216b9-339">The information displayed is as follows:</span></span>

  - <span data-ttu-id="216b9-340">Parkee SIP URI.</span><span class="sxs-lookup"><span data-stu-id="216b9-340">Parkee SIP URI.</span></span>

  - <span data-ttu-id="216b9-341">Parker SIP URI.</span><span class="sxs-lookup"><span data-stu-id="216b9-341">Parker SIP URI.</span></span>

  - <span data-ttu-id="216b9-342">Имя хозяина CPS, где был припаркован вызов.</span><span class="sxs-lookup"><span data-stu-id="216b9-342">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="216b9-343">Отметка времени, когда вызов был извлечен или отброшен.</span><span class="sxs-lookup"><span data-stu-id="216b9-343">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="216b9-344">**-t \<n\>** параметр — тесты, замеряющие орбиту в базе данных, чтобы показать случайность заданных номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="216b9-344">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-345">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-345">Output</span></span>

<span data-ttu-id="216b9-346">В зависимости от параметров ввода, указанных в командной подсказке, call Parkometer отображает следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="216b9-346">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="216b9-347">Все диапазоны орбит, настроенные для этого пула</span><span class="sxs-lookup"><span data-stu-id="216b9-347">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="216b9-348">В настоящее время припаркованные вызовы</span><span class="sxs-lookup"><span data-stu-id="216b9-348">Currently parked calls</span></span>

- <span data-ttu-id="216b9-349">Количество бесплатных (доступных) орбит</span><span class="sxs-lookup"><span data-stu-id="216b9-349">Number of free (available) orbits</span></span>

- <span data-ttu-id="216b9-350">Недавно припаркованные вызовы</span><span class="sxs-lookup"><span data-stu-id="216b9-350">Recently parked calls</span></span>

- <span data-ttu-id="216b9-351">Зарезервированные орбиты для тестирования значений единой и случайной орбиты</span><span class="sxs-lookup"><span data-stu-id="216b9-351">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-352">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-352">Purpose</span></span>

<span data-ttu-id="216b9-353">Целью средства CPS является предоставление командного доступа к базе данных CPS.</span><span class="sxs-lookup"><span data-stu-id="216b9-353">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="216b9-354">Администратор может просмотреть использование CPS и определить количество орбит, назначенных пулу.</span><span class="sxs-lookup"><span data-stu-id="216b9-354">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-355">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-355">Requirements</span></span>

<span data-ttu-id="216b9-356">Нет никаких требований, если этот инструмент запущен на том же компьютере, где работает CPS.</span><span class="sxs-lookup"><span data-stu-id="216b9-356">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="216b9-357">Если этот инструмент работает на удаленном компьютере, SQL Server базы данных, используемой Skype для бизнеса Server 2015 г., необходимо настроить, чтобы разрешить удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="216b9-357">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="216b9-358">Для подключения к SQL Server необходимо настроить SQL Server для подключения к SQL Server базы данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-358">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="216b9-359">Эта SQL Server для подключения к базе данных определяется в файле конфигурации **parkometer.exe.config**. Он должен быть размещен в том же каталоге, parkometer.exe находится.</span><span class="sxs-lookup"><span data-stu-id="216b9-359">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="216b9-360">Следующий XML-файл является примером parkometer.exe.config. Параметры, которые необходимо настроить, это имя пользователя (например, mydomain\Administrator), пароль (например, mypassword) и имя хозяина (например, myserver).</span><span class="sxs-lookup"><span data-stu-id="216b9-360">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="216b9-361">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-361">Examples</span></span>

<span data-ttu-id="216b9-362">Развернутые диапазоны орбит: параметр -o перечисляет все диапазоны орбит, настроенные для этого пула, как показано</span><span class="sxs-lookup"><span data-stu-id="216b9-362">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Диапазоны орбит в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="216b9-364">В настоящее время припаркованные вызовы: параметр -n перечисляет все используемые в настоящее время орбиты в этом пуле, как показано</span><span class="sxs-lookup"><span data-stu-id="216b9-364">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![В настоящее время припаркованные вызовы в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="216b9-366">Количество свободных орбит: параметр -f перечисляет количество свободных в настоящее время орбит в пуле, как показано</span><span class="sxs-lookup"><span data-stu-id="216b9-366">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Бесплатные орбиты в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="216b9-368">Недавно припаркованные вызовы: параметр -r \<n\> перечисляет последние \<n\> припаркованные вызовы, как показано</span><span class="sxs-lookup"><span data-stu-id="216b9-368">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Недавно припаркованные вызовы в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="216b9-370">Тестирование резервирования орбиты: параметр -t тестирует резервирование орбиты \<n\> в базе данных, как показано</span><span class="sxs-lookup"><span data-stu-id="216b9-370">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Тестирование резервирования орбиты в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="216b9-372">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-372">Summary</span></span>

<span data-ttu-id="216b9-373">Call Parkometer — это средство командной строки, которое предоставляет подробные сведения о сервере Call Park Server.</span><span class="sxs-lookup"><span data-stu-id="216b9-373">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="216b9-374">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="216b9-374">DBAnalyze</span></span>
<span data-ttu-id="216b9-375"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-375"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="216b9-376">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-376">Description</span></span>

<span data-ttu-id="216b9-377">DBAnalyze — это средство командной строки, которое помогает администраторам собирать аналитические отчеты о базах данных Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-377">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="216b9-378">DBAnalyze имеет следующие режимы: диагностика, данные пользователей, конференция, фрагментация mcUs и диска:</span><span class="sxs-lookup"><span data-stu-id="216b9-378">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="216b9-379">**Диагностический режим** Создает отчет, который содержит сведения о таблицах (количество записей, фрагментация, размер данных и размер индекса, размеры файлов данных и журналов, последнее время архивации, распределение контактов между серверами, работающими на сервере Microsoft Office Communications Server, среднее число разрешений, контактов, контейнеров, подписок, публикаций, конечных точек на одного пользователя, любых неправильно домашних пользователей, пользователей, которые не могут быть маршрутизованы, среднее число конференций, организованных для каждого пользователя, запланированные конференции, активные конференции и версия базы данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-379">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="216b9-380">Режим диагностики может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="216b9-380">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="216b9-381">**Режим пользовательских данных** Отчеты о контактах, контейнерах, подписке, публикации, разрешении и данных контактной группы для указанного пользователя или пользователей, которые имеют этого пользователя в списках контактов и разрешений.</span><span class="sxs-lookup"><span data-stu-id="216b9-381">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="216b9-382">Этот режим также сообщает сводные данные для конференций, которые пользователь организует или приглашает.</span><span class="sxs-lookup"><span data-stu-id="216b9-382">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="216b9-383">**Режим конференции** Сообщает подробные данные для конкретной конференции, включая все сведения о расписаниях конференции, список приглашенных, список типов мультимедиа, разрешенных для конференции, активные mcUs (блоки управления несколькими точками), список активных участников и состояние сигнала каждого участника.</span><span class="sxs-lookup"><span data-stu-id="216b9-383">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="216b9-384">**Код ID собрания** Расшифровка кода общего номера телефонной сети (PSTN) для собрания, заданного коммутатором **/pstnid,** но не подключаемого к задней части для получения подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="216b9-384">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="216b9-385">**Конференция resolve** Декодирует ID собрания PSTN, заданный коммутатором **/pstnid,** и отображает сведения о конференции, указанной в ID.</span><span class="sxs-lookup"><span data-stu-id="216b9-385">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="216b9-386">**Режим MCUs** Отчеты о ID, типе мультимедиа, URL-адресе, состоянии сердцебиения, нагрузке на конференцию и загрузке участника для каждого MCU в пуле.</span><span class="sxs-lookup"><span data-stu-id="216b9-386">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="216b9-387">**Режим фрагментации диска** Отображает состояние фрагментации всех дисков.</span><span class="sxs-lookup"><span data-stu-id="216b9-387">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="216b9-388">Этот инструмент можно использовать для диагностики различных проблем или для оказания помощи администраторам в планировании емкости.</span><span class="sxs-lookup"><span data-stu-id="216b9-388">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="216b9-389">Например, если большинство пользователей, уехав на сервер A, выбирают в качестве контактов пользователей на сервере B, администратор может переместить пользователей на сервер A на сервер B, чтобы уменьшить трафик на меж сервере.</span><span class="sxs-lookup"><span data-stu-id="216b9-389">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-390">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-390">Output</span></span>

<span data-ttu-id="216b9-391">Этот инструмент выводит предварительные отчеты о базе данных Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-391">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="216b9-392">**Путь:**%ProgramFiles%\Skype для бизнеса Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="216b9-392">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-393">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-393">Purpose</span></span>

<span data-ttu-id="216b9-394">Чтобы установить Dbanalyze.exe, скопируйте его в локализованную папку и запустите средство.</span><span class="sxs-lookup"><span data-stu-id="216b9-394">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="216b9-395">Чтобы использовать средство, запустите следующую команду из командной строки.</span><span class="sxs-lookup"><span data-stu-id="216b9-395">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="216b9-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Ниже показаны описания параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="216b9-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Параметры командной строки для Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="216b9-398">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-398">Requirements</span></span>

 <span data-ttu-id="216b9-399">**Компьютер** DBAnalyze можно запускать только с компьютера, подключитого к домену, который Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-399">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="216b9-400">**Сеть** Компьютер должен иметь возможность подключения к базе данных задней части.</span><span class="sxs-lookup"><span data-stu-id="216b9-400">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="216b9-401">**Компоненты** Skype для бизнеса Server программного обеспечения 2015 года должны быть установлены перед запуском DBAnalyze.</span><span class="sxs-lookup"><span data-stu-id="216b9-401">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="216b9-402">**Пользователи** В приведенной ниже таблице показаны администраторы, у которых есть необходимые разрешения на доступ к базам данных Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-402">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Таблица разрешений для Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="216b9-404">Для режима **/report:disk** требуется учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="216b9-404">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-405">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-405">Examples</span></span>

<span data-ttu-id="216b9-406">Ниже приводится пример допустимых Dbanalyze.exe команд:</span><span class="sxs-lookup"><span data-stu-id="216b9-406">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="216b9-407">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-407">Summary</span></span>

<span data-ttu-id="216b9-408">DBAnalyzer обеспечивает администраторам быстрый и простой анализ баз данных Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-408">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="216b9-409">Импорт служба хранилища данных службы</span><span class="sxs-lookup"><span data-stu-id="216b9-409">Import Storage Service Data</span></span>
<span data-ttu-id="216b9-410"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-410"><a name="Issd"> </a></span></span>

<span data-ttu-id="216b9-411">Средство набора ресурсов ImportStorageServiceData позволяет повторно возвращать данные очереди и конечных точек, которые были смыты из службы служба хранилища (LYSS) обратно в службу служба хранилища.</span><span class="sxs-lookup"><span data-stu-id="216b9-411">The ImportStorageServiceData resource kit tool allows for reimporting Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-412">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-412">Description</span></span>

<span data-ttu-id="216b9-413">Данные, вымытые из служба хранилища службы, могли быть автоматическими (периодическими) в зависимости от состояния элемента очереди или размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-413">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="216b9-414">Это могло произойти из-за ручного вызова комлета обрушения пула или cmdlet StorageServiceFullFlush (который вызывается в пуле).</span><span class="sxs-lookup"><span data-stu-id="216b9-414">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="216b9-415">Обратите внимание, что данные в идеале не следует возвращать, если размер базы данных службы служба хранилища (LYSS) на передних концах превышает обычный уровень, так как это, скорее всего, приведет к обратному экспорту дополнительных данных. Кроме того, необходимо сначала устранить все проблемы, которые могли привести к ошибкам, которые привели к росту очереди служба хранилища службы (например, ошибки конечной точки Exchange, сетевые проблемы или другие проблемы).</span><span class="sxs-lookup"><span data-stu-id="216b9-415">Note that data should ideally not be reimported if any of the Storage Service (LYSS ) database sizes on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems that could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="216b9-416">**Сценарий 1.** При сбойе пула файлы могут быть смыть из службы хранения для каждого переднего конца.</span><span class="sxs-lookup"><span data-stu-id="216b9-416">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="216b9-417">После завершения сбой необходимо запустить средство для повторной передачи данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-417">After failover is completed, the tool should be run to reimport the data.</span></span>

 <span data-ttu-id="216b9-418">**Сценарий 2:** данные сбрасываются автоматически каждый день или в ответ на служба хранилища базы данных службы, превышающие определенные пороговые значения размера (например, 60%, 80%, 90% полных).</span><span class="sxs-lookup"><span data-stu-id="216b9-418">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds (for example 60%, 80%, 90% full).</span></span> <span data-ttu-id="216b9-419">Эти автоматически сбрасываемые данные должны регулярно перенаправлены администратором.</span><span class="sxs-lookup"><span data-stu-id="216b9-419">This automatically flushed data should be reimported routinely by the administrator.</span></span> <span data-ttu-id="216b9-420">В вышеуказанной ситуации, если пакет мониторинга SCOM не развернут, для службы Skype для бизнеса Server служба хранилища события, связанные с очисткой данных из службы служба хранилища.</span><span class="sxs-lookup"><span data-stu-id="216b9-420">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="216b9-421">ID-данных событий 32075 (запущена полная операция флеша), 32076 (полный флеш завершен), 32082 (запущен флеш уровня обслуживания), 32083 (полное завершение очистки уровня обслуживания), 32089 (флеш произошел из-за заполнения базы данных).</span><span class="sxs-lookup"><span data-stu-id="216b9-421">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="216b9-422">Обратите внимание, что эти Ids событий соответствуют выпуску RTM.</span><span class="sxs-lookup"><span data-stu-id="216b9-422">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="216b9-423">Когда администратор видит эти события, это означает, что есть файлы, которые были выбросываются. Эти данные следует регулярно импортировать обратно с помощью этого средства, например один раз в неделю.</span><span class="sxs-lookup"><span data-stu-id="216b9-423">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="216b9-424">Для выпуска online-службы, если развертывается пакет SCOM для мониторинга состояния Skype для бизнеса Server, могут быть подняты новые оповещения, которые просят администратора повторно перенаправление смытых данных обратно в службу служба хранилища Service.</span><span class="sxs-lookup"><span data-stu-id="216b9-424">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts that may be raised which ask the administrator to reimport the flushed data back into Storage Service.</span></span> <span data-ttu-id="216b9-425">Соответствующее событие будет в журнале событий на Front-End, который вызвал оповещение.</span><span class="sxs-lookup"><span data-stu-id="216b9-425">There will be a corresponding event in the event log on the Front-End server that triggered the alert.</span></span> <span data-ttu-id="216b9-426">Событие даст описание родительского пути, в соответствии с которым находятся файлы данных с очисткой, а также количество файлов, которые соответствуют критериям оповещения.</span><span class="sxs-lookup"><span data-stu-id="216b9-426">The event will give a description of the Parent path under which the flushed data files are located, and how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="216b9-427">Критерии оповещения в том, что под определенным родительским путем находятся X или несколько файлов, которым не менее Y дней (где X и Y предварительно заданы в StorageService, но могут быть переопределены путем изменения файла APPCONFIG.) Ниже показаны два примера событий, которые могут вызвать оповещение о состоянии здоровья, при этом разница заключается в родительском пути.</span><span class="sxs-lookup"><span data-stu-id="216b9-427">The alert criteria is that there are X or more files under the particular parent path that are at least Y days old (where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events that can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="216b9-428">Одна из возможностей находится в файле веб-службы, а другая — в локальном каталоге данных приложений для каждого переднего конца.</span><span class="sxs-lookup"><span data-stu-id="216b9-428">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="216b9-429">(например, c:\ProgramData\Microsoft\Skype для бизнеса Server 2015\StorageService).</span><span class="sxs-lookup"><span data-stu-id="216b9-429">(for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService).</span></span> <span data-ttu-id="216b9-430">Затем администратор запустит этот инструмент reskit.</span><span class="sxs-lookup"><span data-stu-id="216b9-430">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="216b9-431">Этот инструмент увеличит нагрузку ЦП и IO на переднем конце, на который он запущен, и на других передних концах в ситуации, когда данные не принадлежат переднему концу, на который выполняется инструмент.</span><span class="sxs-lookup"><span data-stu-id="216b9-431">This tool will increase CPU and IO load on the front end it is running on, and other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="216b9-432">Рекомендуется использовать этот инструмент, если передние концы не находятся под нагрузкой на ЦП и IO, например за пределами пиковых часов.</span><span class="sxs-lookup"><span data-stu-id="216b9-432">We recommend running this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="216b9-433">Во-вторых, этот инструмент может импортировать один файл данных от 2 до 3 минут.</span><span class="sxs-lookup"><span data-stu-id="216b9-433">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="216b9-434">Помните об этом при оценке продолжительного запуска инструмента.</span><span class="sxs-lookup"><span data-stu-id="216b9-434">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="216b9-435">Многословный файл журнала, созданный средством, по умолчанию появится в Хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="216b9-435">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="216b9-436">Удалите его, если не будет сообщений об ошибках, так как файл журнала может быть десятками МБ или более.</span><span class="sxs-lookup"><span data-stu-id="216b9-436">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Пример служба хранилища событий журнала событий Server.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="216b9-438">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-438">Requirements</span></span>

<span data-ttu-id="216b9-439">Установите инструменты Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-439">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="216b9-440">Средство работает на компьютерах, присоединимых к домену, Skype для бизнеса Server и Skype для бизнеса Server службы управления.</span><span class="sxs-lookup"><span data-stu-id="216b9-440">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="216b9-441">Средство использует командылет из оболочки управления для идентификации всех Front-End серверов пула.</span><span class="sxs-lookup"><span data-stu-id="216b9-441">The tool uses a cmdlet from the management shell to identify all the Front-End servers in the pool.</span></span> <span data-ttu-id="216b9-442">Во-вторых, инструмент должен выполняться с компьютера в пуле с установленной базой **данных RtcLocal.**</span><span class="sxs-lookup"><span data-stu-id="216b9-442">Secondly, the tool must be executed from a machine in the pool that has the **RtcLocal** database installed.</span></span> <span data-ttu-id="216b9-443">Эта база данных используется средством для получения расположения файла WEBSERVICE для пула.</span><span class="sxs-lookup"><span data-stu-id="216b9-443">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="216b9-444">Кроме того, перед использованием средства каждый сервер Front-End сначала должен включить Windows PowerShell повторное использование **enable-PSRemoting** на каждом Front-End сервере, а также машину, на которую выполняется инструмент.</span><span class="sxs-lookup"><span data-stu-id="216b9-444">Additionally, before using the tool, each Front-End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front-End server, and the machine that the tool is executed from.</span></span> <span data-ttu-id="216b9-445">В противном случае Windows PowerShell удаленные команды из этого средства сбой.</span><span class="sxs-lookup"><span data-stu-id="216b9-445">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="216b9-446">Windows PowerShell Перенастройка может быть отключена на всех Front-End серверах пула после ее завершения.</span><span class="sxs-lookup"><span data-stu-id="216b9-446">Windows PowerShell Remoting can be turned off on all Front-End servers in the pool after it is finished.</span></span> <span data-ttu-id="216b9-447">Наконец, у учетной записи или учетных данных, на которые выполнят этот инструмент, должно быть разрешение на чтение и запись в файле веб-службы для пула, на который они выполняют этот инструмент.</span><span class="sxs-lookup"><span data-stu-id="216b9-447">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="216b9-448">В противном случае средство не будет работать с ошибками разрешений IO.</span><span class="sxs-lookup"><span data-stu-id="216b9-448">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="216b9-449">В Windows Server 2012 по умолчанию Windows PowerShell, но не на операционной системе Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="216b9-449">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-450">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-450">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="216b9-451">LCSSync</span><span class="sxs-lookup"><span data-stu-id="216b9-451">LCSSync</span></span>
<span data-ttu-id="216b9-452"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-452"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="216b9-453">Средство LCSSync помогает развернуть Skype для бизнеса Server 2015 г. в многолесной среде.</span><span class="sxs-lookup"><span data-stu-id="216b9-453">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="216b9-454">Этот инструмент используется для синхронизации пользователей и групп из разных лесов пользователей в качестве контактного объекта Службы домена Active Directory в центральный лес, Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-454">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-455">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-455">Description</span></span>

 <span data-ttu-id="216b9-456">LCSSync использует синхронизированные контактные объекты Active Directory Domain Services в центральном лесу, чтобы включить пользователей для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="216b9-456">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="216b9-457">Чтобы обеспечить единый вход, основная учетная запись пользователя должна быть соотнося с контактным объектом Active Directory Domain Services в центральном лесу на Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-457">To provide single sign in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="216b9-458">Этот инструмент помогает выполнять сопоставление.</span><span class="sxs-lookup"><span data-stu-id="216b9-458">This tool helps perform that mapping.</span></span> <span data-ttu-id="216b9-459">Этот инструмент предоставляет шаблоны для создания агентов управления в Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="216b9-459">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="216b9-460">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-460">Summary</span></span>

<span data-ttu-id="216b9-461">Средство LCSSync помогает развернуть Skype для бизнеса Server 2015 г. в многолесной среде.</span><span class="sxs-lookup"><span data-stu-id="216b9-461">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="216b9-462">Консоль пользователя Lookup</span><span class="sxs-lookup"><span data-stu-id="216b9-462">Lookup User Console</span></span>
<span data-ttu-id="216b9-463"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-463"><a name="LUC"> </a></span></span>

<span data-ttu-id="216b9-464">Средство LookupUserConsole отображает внутренние сведения Skype для бизнеса Server маршрутов о конкретных пользователях.</span><span class="sxs-lookup"><span data-stu-id="216b9-464">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="216b9-465">Эти сведения могут быть полезны для личной поддержки Корпорации Майкрософт в диагностике проблем развертывания и маршрутов.</span><span class="sxs-lookup"><span data-stu-id="216b9-465">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-466">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-466">Description</span></span>

 <span data-ttu-id="216b9-467">При LookupUserConsole.exe откроется командная подсказка, которая принимает SIP-адреса и пытается отобразить внутренние Skype для бизнеса Server, связанные с ними.</span><span class="sxs-lookup"><span data-stu-id="216b9-467">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="216b9-468">Введите **выход,** чтобы выйти из инструмента LookupUserConsole.</span><span class="sxs-lookup"><span data-stu-id="216b9-468">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-469">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-469">Requirements</span></span>

<span data-ttu-id="216b9-470">Установите набор Skype для бизнеса Server 2015 года.</span><span class="sxs-lookup"><span data-stu-id="216b9-470">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="216b9-471">Средство работает на компьютерах с доменом, на которых Skype для бизнеса Server установлена система.</span><span class="sxs-lookup"><span data-stu-id="216b9-471">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-472">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-472">Examples</span></span>

<span data-ttu-id="216b9-473">C:\Program Files\Skype для бизнеса Server 2015\ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="216b9-473">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="216b9-474">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="216b9-474">MsTurnPing</span></span>
<span data-ttu-id="216b9-475"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-475"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="216b9-476">Средство MSTurnPing позволяет администратору программного обеспечения связи Skype для бизнеса Server 2015 г. проверять состояние серверов, на которые работают службы проверки подлинности аудио и видео, а также серверы, на которые работают службы политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="216b9-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-477">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-477">Description</span></span>

<span data-ttu-id="216b9-478">Средство MSTurnPing позволяет администратору программного обеспечения связи Skype для бизнеса Server 2015 г. проверять состояние серверов, на которые работают службы проверки подлинности аудио и видео, а также серверы, на которые работают службы политики пропускной способности в топологии.</span><span class="sxs-lookup"><span data-stu-id="216b9-478">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="216b9-479">Средство позволяет администратору выполнять следующие тесты:</span><span class="sxs-lookup"><span data-stu-id="216b9-479">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="216b9-480">Тест A/V Edge Server: средство выполняет тесты для всех серверов A/V Edge Server в топологии, выполняя следующие:</span><span class="sxs-lookup"><span data-stu-id="216b9-480">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="216b9-481">Проверка того, что Skype для бизнеса Server служба проверки подлинности аудио и видео запущена и может выдавать соответствующие учетные данные.</span><span class="sxs-lookup"><span data-stu-id="216b9-481">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="216b9-482">Проверка того, что Skype для бизнеса Server служба аудио- и видеоконферентов запущена и может успешно распределять ресурсы на внешнем краю.</span><span class="sxs-lookup"><span data-stu-id="216b9-482">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="216b9-483">Тест службы политики пропускной способности: средство выполняет тесты на всех серверах, на которые работают службы политики пропускной способности в топологии, выполняя следующие:</span><span class="sxs-lookup"><span data-stu-id="216b9-483">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="216b9-484">Проверка того, что Skype для бизнеса Server служба политики пропускной способности (проверка подлинности) запущена и может выдавать соответствующие учетные данные.</span><span class="sxs-lookup"><span data-stu-id="216b9-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="216b9-485">Проверка того, что Skype для бизнеса Server служба политики пропускной способности (Core) запущена и может успешно выполнять проверку пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="216b9-485">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="216b9-486">Этот инструмент должен запускаться с компьютера, который входит в топологию и имеет локальный магазин.</span><span class="sxs-lookup"><span data-stu-id="216b9-486">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-487">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-487">Output</span></span>

<span data-ttu-id="216b9-488">Средство выводит результаты каждой из операций.</span><span class="sxs-lookup"><span data-stu-id="216b9-488">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="216b9-489">Если **выполняется тест AudioVideoEdgeServer,** выходы инструмента следующие:</span><span class="sxs-lookup"><span data-stu-id="216b9-489">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="216b9-490">Результаты тестирования компьютеров, которые предоставляют службу проверки подлинности Skype для бизнеса Server 2015 г. в топологии</span><span class="sxs-lookup"><span data-stu-id="216b9-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="216b9-491">Результаты тестирования компьютеров, которые предоставляют Skype для бизнеса Server 2015 аудио- и видеоконферент в топологии</span><span class="sxs-lookup"><span data-stu-id="216b9-491">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="216b9-492">Если **выполняется тест BandwidthPolicyServer,** выходы инструмента следующие:</span><span class="sxs-lookup"><span data-stu-id="216b9-492">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="216b9-493">Результаты тестирования компьютеров, которые предоставляют службу политики Skype для бизнеса Server пропускной способности 2015 г. (проверка подлинности) в топологии</span><span class="sxs-lookup"><span data-stu-id="216b9-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="216b9-494">Результаты тестирования компьютеров, которые предоставляют Skype для бизнеса Server 2015 службы политики пропускной способности (Core) в топологии</span><span class="sxs-lookup"><span data-stu-id="216b9-494">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-495">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-495">Requirements</span></span>

- <span data-ttu-id="216b9-496">Этот инструмент должен запускаться с компьютера, который находится в топологии и имеет локальный магазин.</span><span class="sxs-lookup"><span data-stu-id="216b9-496">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="216b9-497">Инструмент должен работать в качестве администратора, который имеет доступ к локальному магазину.</span><span class="sxs-lookup"><span data-stu-id="216b9-497">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-498">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-498">Examples</span></span>

<span data-ttu-id="216b9-499">Ниже приводится пример ввода средства.</span><span class="sxs-lookup"><span data-stu-id="216b9-499">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="216b9-500">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-500">Summary</span></span>

<span data-ttu-id="216b9-501">Этот инструмент может быть ценным ресурсом для Skype для бизнеса Server 2015 г., которые хотят проверить состояние серверов, на которых работают службы политики аудио- и видеосвязи и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="216b9-501">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="216b9-502">Просмотр конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="216b9-502">Network Configuration Viewer</span></span>
<span data-ttu-id="216b9-503"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-503"><a name="NCV"> </a></span></span>

<span data-ttu-id="216b9-504">Средство просмотра конфигурации сети может использоваться администраторами программного обеспечения связи Skype для бизнеса Server 2015 г. для просмотра топологии сетевой топологии управления приемом вызовов (CAC) для предприятия, которое должно разрешить сеансы связи в режиме реального времени, такие как голосовые или видеозвонков на основе указанной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="216b9-504">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="216b9-505">Skype для бизнеса Server 2015 г. администраторы определяют политики CAC, которые применяются службами политики пропускной способности, установленными с Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-505">Skype for Business Server 2015 administrators defines CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-506">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-506">Description</span></span>

<span data-ttu-id="216b9-507">Network Configuration Viewer (NetworkConfigurationViewer.exe) позволяет администраторам выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="216b9-507">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="216b9-508">Загрузка и просмотр сетевой топологии CAC Skype для бизнеса Server 2015 г. в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="216b9-508">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="216b9-509">Загрузка и просмотр сетевой топологии CAC из файла журнала политики пропускной способности Server в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="216b9-509">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="216b9-510">Сохранение и хранение сетевой топологии CAC в формате XML на диске.</span><span class="sxs-lookup"><span data-stu-id="216b9-510">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="216b9-511">Сохранение и хранение схемы топологии сети CAC в формате JPG или BMP.</span><span class="sxs-lookup"><span data-stu-id="216b9-511">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="216b9-512">Просмотр данных конфигурации конфигурации сетевой топологии CAC.</span><span class="sxs-lookup"><span data-stu-id="216b9-512">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="216b9-513">Просмотр топологии сети CAC в стиле представления дерева.</span><span class="sxs-lookup"><span data-stu-id="216b9-513">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="216b9-514">Определите настраиваемые соединители для ссылок сетевой топологии CAC (например, ссылок от сайта к региону, региона к региону и ссылок на сайт).</span><span class="sxs-lookup"><span data-stu-id="216b9-514">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="216b9-515">Просмотр сведений о сетевой топологии cac, сведений о регионах и политик пропускной способности и сетевых ссылок.</span><span class="sxs-lookup"><span data-stu-id="216b9-515">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-516">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-516">Purpose</span></span>

<span data-ttu-id="216b9-517">Просмотр корпоративных сетевых топологий CAC в графическом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="216b9-517">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-518">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-518">Examples</span></span>

 <span data-ttu-id="216b9-519">Загрузка и просмотр топологии сети CAC с **развертывания Skype для бизнеса Server 2015** г. в графическом формате: Skype для бизнеса Server 2015 г. администраторы могут загружать и просматривать конфигурацию сетевой топологии CAC на любом компьютере Skype для бизнеса Server 2015 г., используя параметр **Конфигурация** сети загрузки, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-519">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="216b9-520">Средство не сможет скачать или просмотреть такую конфигурацию при развертывании на компьютере, не подключенном к хранилище конфигураций Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-520">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Загрузка конфигурации сети.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="216b9-522">Загрузка и просмотр сетевой топологии CAC из файла журнала журнала политики пропускной способности в графическом **формате:** Skype для бизнеса Server 2015 г. Серверы политики пропускной способности экономят топологию сети CAC в рамках механизма ведения журнала в соответствии с расположением файла Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-522">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers saves the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="216b9-523">Skype для бизнеса Server 2015 г. администраторы могут просматривать такой файл в графическом формате с помощью параметра **Open Network Configuration,** как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-523">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Открытие файла журнала политики пропускной способности Сервера.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="216b9-525">Сохранение и хранение сетевой топологии CAC в формате XML на диске: администраторы Skype для бизнеса Server 2015 г. могут сохранить файл конфигурации сетевой топологии CAC в формате XML с помощью варианта **Сохранить** копию параметра конфигурации сети, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-525">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="216b9-526">Сохраненный файл конфигурации можно использовать в автономном режиме для графического просмотра.</span><span class="sxs-lookup"><span data-stu-id="216b9-526">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Сохранение конфигурации сети в качестве XML-файла.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="216b9-528">Сохранение и хранение схемы топологии сети CAC в формате JPG или BMP: администраторы Skype для бизнеса Server 2015 г. могут сохранить конфигурацию топологии  сети CAC в графическом формате (форматы файлов JPG и BMP) с помощью схемы Сохранить конфигурацию сети в качестве варианта изображения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-528">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Сохранение конфигурации сети в качестве изображения.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="216b9-530">Просмотр данных конфигурации сетевой топологии <strong>cac:</strong>Skype для бизнеса Server 2015 г. Администраторы могут просматривать связанные данные конфигурации сети, такие как сетевые регионы, сетевые сайты, профили пропускной способности и IP-адреса подсети сайта в текстовом формате с помощью параметра Конфигурация сети просмотра, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-530"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Просмотр данных конфигурации сети.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="216b9-532">**Просмотр топологии** сети CAC в стиле представления дерева: Skype для бизнеса Server 2015 г. администраторы могут просматривать связанные данные конфигурации сети в стиле представления графического дерева с помощью панели управления слева от окна инструмента, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-532">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Просмотр данных конфигурации сети в представлении дерева.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="216b9-534">Определите настраиваемые соединители для ссылок топологии сети **CAC (например,** ссылки от сайта к региону, региону к региону и ссылки на сайт): администраторы Skype для бизнеса Server 2015 г. могут определять настраиваемые графические соединители для ссылок конфигурации сети CAC с помощью параметра Параметры, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-534">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="216b9-535">Это позволяет различать различные типы сетевых ссылок, которые предусмотрены в конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="216b9-535">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Инструменты](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="216b9-537">Просмотр сведений о сайте топологии сети **CAC,** сведений о регионах и политик пропускной способности: администраторы Skype для бизнеса Server 2015 г. могут просматривать связанные сведения о сетевом регионе CAC, сведения о сайте и сведения о пропускной способности CAC с помощью параметров, показанных ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-537">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="216b9-538">(Например, щелкните **Info** в сетевом регионе или объекте сетевого сайта.)</span><span class="sxs-lookup"><span data-stu-id="216b9-538">(For example, click **Info** in a network region or network site object.)</span></span>

![Определение настраиваемой соединители для вашей сети.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="216b9-540">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-540">Summary</span></span>

<span data-ttu-id="216b9-541">Этот инструмент может быть ценным ресурсом для администраторов 2015 Skype для бизнеса Server 2015 года, которые хотели бы просмотреть топологию сети CAC для их развертывания в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="216b9-541">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="216b9-542">Агент группы ответов в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="216b9-542">Response Group Agent Live</span></span>
<span data-ttu-id="216b9-543"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-543"><a name="RGAL"> </a></span></span>

<span data-ttu-id="216b9-544">Приложение Response Group предоставляет агентам возможность получать доступ к полезной информации в режиме реального времени с помощью встроенной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="216b9-544">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="216b9-545">К сожалению, за пределами приложения отсутствует графическое представление этих данных.</span><span class="sxs-lookup"><span data-stu-id="216b9-545">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="216b9-546">Средство Набора живых ресурсов группы ответов позволяет решить эту проблему, предоставляя простой и графический способ доступа к этой информации, расширенный с помощью данных программного обеспечения для Skype для бизнеса связи, таких как присутствие других агентов.</span><span class="sxs-lookup"><span data-stu-id="216b9-546">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-547">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-547">Description</span></span>

<span data-ttu-id="216b9-548">Агент Группы откликов — это Windows приложение, которое предоставляет агентам группы реагирования функции входов и регистрации, а также некоторые сведения в режиме реального времени (например, членство в группе и текущее количество вызовов).</span><span class="sxs-lookup"><span data-stu-id="216b9-548">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="216b9-549">Она предназначена для расширенной версии страницы Группы агентов (доступной из Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="216b9-549">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-550">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-550">Purpose</span></span>

<span data-ttu-id="216b9-551">Приложение Группы реагирования ставит в очередь входящие вызовы, а затем передает их в группы агентов.</span><span class="sxs-lookup"><span data-stu-id="216b9-551">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="216b9-552">Для принятия обоснованных решений о том, какие вызовы для службы, агенты могут получать доступ к сведениям о группах агентов в режиме реального времени, например о доступных агентах и о том, сколько вызовов ожидается в каждой очереди.</span><span class="sxs-lookup"><span data-stu-id="216b9-552">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="216b9-553">Эта информация, изначально доступная только через службу группы реагирования, интуитивно доступна агентом группы реагирования Live.</span><span class="sxs-lookup"><span data-stu-id="216b9-553">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="216b9-554">Функции</span><span class="sxs-lookup"><span data-stu-id="216b9-554">Features</span></span>

<span data-ttu-id="216b9-555">Средство Agent Live группы ответов построено на службе Группы отклика и Skype для бизнеса Server SDK 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-555">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="216b9-556">Она предоставляет агентам группы реагирования сведения и возможности, доступные из службы Группы реагирования (например, членство в группе, присутствие других агентов и количество ожидающих вызовов).</span><span class="sxs-lookup"><span data-stu-id="216b9-556">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="216b9-557">На рисунке ниже иллюстрируется основной интерфейс агента группы ответов Live.</span><span class="sxs-lookup"><span data-stu-id="216b9-557">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Средство Агента группы отклика в прямом эфире.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="216b9-559">Следующие три основных функции доступны для агентов в агенте группы реагирования в Live:</span><span class="sxs-lookup"><span data-stu-id="216b9-559">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="216b9-560">**Вход/выход:** В отличие от страницы Группы агентов (доступной с Skype для бизнеса Server 2015 г.), агент Группы ответов позволяет только агентам одновременно войти или выйти из всех групп агентов.</span><span class="sxs-lookup"><span data-stu-id="216b9-560">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign in or out of all agent groups at once.</span></span> <span data-ttu-id="216b9-561">Это приложение предоставляет три быстрых способа для агентов, чтобы войти или выйти:</span><span class="sxs-lookup"><span data-stu-id="216b9-561">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="216b9-562">Щелкните кнопки Вход и выход (зеленый и красный) в приложении.</span><span class="sxs-lookup"><span data-stu-id="216b9-562">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="216b9-563">Щелкните правой кнопкой мыши значок лотка системы и выберите вход или выход.</span><span class="sxs-lookup"><span data-stu-id="216b9-563">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="216b9-564">Использование настраиваемых ярлыков клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="216b9-564">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="216b9-565">**Членство в группе:** Когда выбрана группа агентов, агент группы реагирования в прямом эфире отображает список агентов в этой группе в правой области.</span><span class="sxs-lookup"><span data-stu-id="216b9-565">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="216b9-566">Если Skype для бизнеса Server 2015 работает на том же компьютере, что и это приложение, сведения о присутствии и контактная карточка отображаются в агенте группы реагирования Live.</span><span class="sxs-lookup"><span data-stu-id="216b9-566">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="216b9-567">Агенты могут отправлять мгновенный вызов или вызывать других агентов непосредственно оттуда.</span><span class="sxs-lookup"><span data-stu-id="216b9-567">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="216b9-568">**Статистика в режиме реального времени:** Агент группы реагирования Live предоставляет статистику в режиме реального времени для всех групп агентов.</span><span class="sxs-lookup"><span data-stu-id="216b9-568">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="216b9-569">Частота обновления — одна минута.</span><span class="sxs-lookup"><span data-stu-id="216b9-569">The update frequency is one minute.</span></span> <span data-ttu-id="216b9-570">Когда на вызов отвечает группа ответа, рядом с именем группы добавляется визуальный индикатор с текущим числом очередных вызовов.</span><span class="sxs-lookup"><span data-stu-id="216b9-570">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="216b9-571">Приодержание указателя над группой также отображает самое длительное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="216b9-571">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-572">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-572">Requirements</span></span>

<span data-ttu-id="216b9-573">Агент группы ответов Live требует платформа .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="216b9-573">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="216b9-574">Кроме того, чтобы воспользоваться возможностями присутствия и контактной карточки, необходимо установить Skype для бизнеса локально (и запускать).</span><span class="sxs-lookup"><span data-stu-id="216b9-574">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="216b9-575">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="216b9-575">Configuration</span></span>

<span data-ttu-id="216b9-576">Агент Группы отклика Агент Live может быть настроен на индивидуальные предпочтения с помощью диалогового окна Options в приложении.</span><span class="sxs-lookup"><span data-stu-id="216b9-576">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="216b9-577">Кроме того, администратор может определить хост-адрес по умолчанию путем непосредственного редактирования свойства defaultHostAddress RGAgentLive.exe.config файла.</span><span class="sxs-lookup"><span data-stu-id="216b9-577">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="216b9-578">На рисунке ниже иллюстрирует диалоговое окно Options, которое агенты могут использовать для настройки адреса хоста и клавиш ярлыков.</span><span class="sxs-lookup"><span data-stu-id="216b9-578">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="216b9-579">Этот диалоговое окно можно получить, нажав кнопку Параметры в правом верхнем справа от основного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="216b9-579">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Диалоговое окно Агент Live Options группы ответов.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="216b9-581">Следующие три различных параметра могут быть настроены в конфигурации Агента группы реагирования в Live:</span><span class="sxs-lookup"><span data-stu-id="216b9-581">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="216b9-582">Адрес хост. Обычно это веб-пул FQDN, принадлежащий домашнему пулу агента.</span><span class="sxs-lookup"><span data-stu-id="216b9-582">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="216b9-583">Точный адрес службы группы реагирования автоматически выводится в фоновом режиме из этой информации (путем придания нужного пути после хоста).</span><span class="sxs-lookup"><span data-stu-id="216b9-583">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="216b9-584">Ярлыки. Точные ярлыки для входов и выходов можно настроить.</span><span class="sxs-lookup"><span data-stu-id="216b9-584">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="216b9-585">Единственным ограничением является то, что оба ярлыка должны содержать ключ "Windows Logo" (в дополнение по крайней мере к другому ключу).</span><span class="sxs-lookup"><span data-stu-id="216b9-585">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="216b9-586">Начните с Windows: приложение можно настроить для автоматического запуска с Windows.</span><span class="sxs-lookup"><span data-stu-id="216b9-586">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-587">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-587">Examples</span></span>

<span data-ttu-id="216b9-588">На рисунке ниже показано, как вызвать или отправить мгновенный вызов другому агенту, щелкнув правой кнопкой мыши контакт в правой области.</span><span class="sxs-lookup"><span data-stu-id="216b9-588">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Вызов или отправка мгновенных сообщений.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="216b9-590">На рисунке ниже показано, как агент Группы ответов в Прямом эфире отображает текущее число вызовов в очереди и самое длительное время ожидания среди всех этих входящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="216b9-590">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Просмотр сведений о очереди.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="216b9-592">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-592">Summary</span></span>

<span data-ttu-id="216b9-593">Быстрый вход и вход, членство в группе и базовая статистика в режиме реального времени — это интересные функции агента группы реагирования, доступные только за пределами приложения из службы группы реагирования.</span><span class="sxs-lookup"><span data-stu-id="216b9-593">Fast sign in and sign out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="216b9-594">С помощью средства набора живых ресурсов группы ответов Skype для бизнеса Server 2015 г. администраторы могут предоставить своим агентам Windows приложение, которое позволяет им выполнять задачи более быстрым и графическим способом.</span><span class="sxs-lookup"><span data-stu-id="216b9-594">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="216b9-595">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="216b9-595">SEFAUtil</span></span>
<span data-ttu-id="216b9-596"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-596"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="216b9-597">SEFAUtil (активация дополнительных функций расширения) — это средство командной строки, которое позволяет администраторам программного обеспечения связи Skype для бизнеса Server 2015 г. и агентам helpdesk настраивать для пользователя Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-597">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="216b9-598">Этот инструмент также позволяет администраторам запрашивать параметры маршрутизов вызовов, опубликованные для конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-598">The tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="216b9-599">Средство SEFAUtil позволяет администратору включить/отключить/изменить переадправление вызовов или одновременно звонить от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-599">The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="216b9-600">Администратор может указать цель (в виде SIP URI) или использовать цель, которая уже опубликована пользователем.</span><span class="sxs-lookup"><span data-stu-id="216b9-600">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="216b9-601">Этот инструмент также позволяет администраторам добавлять или удалять делегатов или членов группы по вызову группы от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-601">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.</span></span> <span data-ttu-id="216b9-602">Этот инструмент построен на API управляемых единой связи Майкрософт (UCMA) 3.0 и требует, чтобы администраторы создали надежное приложение в центральном хранилище управления для SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="216b9-602">This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="216b9-603">SEFAUtil (активация дополнительных функций расширения) позволяет администраторам Skype для бизнеса Server 2015 г. и агентам helpdesk настраивать для пользователя Skype для бизнеса Server 2015 г. одновременный звон, одновременный звонок, параметры командного вызова и сбор групповых вызовов от имени пользователя Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-603">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="216b9-604">Этот инструмент также позволяет администраторам запрашивать параметры маршрутивки вызовов, опубликованные для конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-604">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-605">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-605">Description</span></span>

<span data-ttu-id="216b9-606">Текущая версия SEFAUtil — это только средство командной строки; нет поддерживающих графических пользовательских интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="216b9-606">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="216b9-607">Этот инструмент основан на microsoft Unified Communications Managed API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="216b9-607">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="216b9-608">Функции этого средства позволяют администраторам и агентам helpdesk делать следующие функции:</span><span class="sxs-lookup"><span data-stu-id="216b9-608">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="216b9-609">Просмотр всех параметров маршрутирования вызовов для пользователя (включает переададку, делегирования, одновременный звонок, вызов группы и групповой вызов)</span><span class="sxs-lookup"><span data-stu-id="216b9-609">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call, and group call pickup)</span></span>

- <span data-ttu-id="216b9-610">Параметр Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span><span class="sxs-lookup"><span data-stu-id="216b9-610">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="216b9-611">Включить/отключить/изменить непосредственные конфигурации переададации вызовов</span><span class="sxs-lookup"><span data-stu-id="216b9-611">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="216b9-612">Включить/отключить или изменить параметры делегирования</span><span class="sxs-lookup"><span data-stu-id="216b9-612">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="216b9-613">Включить/отключить или изменить параметры групп групп по вызову группы</span><span class="sxs-lookup"><span data-stu-id="216b9-613">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="216b9-614">Новый инструмент Skype для бизнеса Server SEFAUtil 2015</span><span class="sxs-lookup"><span data-stu-id="216b9-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="216b9-615">Включить/отключить/изменить параметры одновременного звона (включает пункт назначения)</span><span class="sxs-lookup"><span data-stu-id="216b9-615">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="216b9-616">Новый инструмент Skype для бизнеса Server SEFAUtil 2015</span><span class="sxs-lookup"><span data-stu-id="216b9-616">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="216b9-617">Включить/отключить или изменить параметры группового вызова</span><span class="sxs-lookup"><span data-stu-id="216b9-617">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="216b9-618">Новый инструмент Skype для бизнеса Server SEFAUtil 2015</span><span class="sxs-lookup"><span data-stu-id="216b9-618">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="216b9-619">Этот инструмент имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="216b9-619">This tool has the following limitations:</span></span>

- <span data-ttu-id="216b9-620">Поддерживается только для пользователей, Skype для бизнеса Server пула</span><span class="sxs-lookup"><span data-stu-id="216b9-620">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="216b9-621">Массовая правка параметров маршрутивки вызовов для нескольких пользователей не поддерживается</span><span class="sxs-lookup"><span data-stu-id="216b9-621">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="216b9-622">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-622">Output</span></span>

<span data-ttu-id="216b9-623">Текущая версия этого средства обеспечивает выход только в окне Командная подсказка.</span><span class="sxs-lookup"><span data-stu-id="216b9-623">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="216b9-624">Подробные сведения см. в разделе Примеры в этом документе.</span><span class="sxs-lookup"><span data-stu-id="216b9-624">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-625">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-625">Purpose</span></span>

<span data-ttu-id="216b9-626">Ниже приводится несколько ключевых сценариев, в которых этот инструмент может использоваться:</span><span class="sxs-lookup"><span data-stu-id="216b9-626">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="216b9-627">Боб является руководителем и был перемещен в Skype для бизнеса Server телефонии.</span><span class="sxs-lookup"><span data-stu-id="216b9-627">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="216b9-628">У него есть делегирования в существующей системе PBX.</span><span class="sxs-lookup"><span data-stu-id="216b9-628">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="216b9-629">В рамках переезда Skype для бизнеса Server 2015 г. администратор может настроить маршрутику Боба, чтобы отразить его уже существующую конфигурацию делегирования.</span><span class="sxs-lookup"><span data-stu-id="216b9-629">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="216b9-630">Алиса путешествует и понимает, что ожидает важного звонка от одного из своих клиентов.</span><span class="sxs-lookup"><span data-stu-id="216b9-630">Alice is traveling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="216b9-631">Однако она находится в гостинице и не имеет доступа к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="216b9-631">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="216b9-632">Она вызывает справку и просит переадлить на ее мобильный номер все вызовы, сделанные на ее рабочий номер.</span><span class="sxs-lookup"><span data-stu-id="216b9-632">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="216b9-633">Персонал helpdesk может сделать конфигурацию от ее имени.</span><span class="sxs-lookup"><span data-stu-id="216b9-633">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="216b9-634">Звонки Джо на его рабочий номер идут на его мобильную голосовую почту всякий раз, когда он находится на работе; однако, как представляется, все работает правильно в большинстве других мест.</span><span class="sxs-lookup"><span data-stu-id="216b9-634">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="216b9-635">Техник helpdesk может просматривать конфигурацию маршрутики Джо и обнаруживает, что у Джо есть одновременный звонок, настроенный на его мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="216b9-635">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="216b9-636">Техник спрашивает Джо о мобильном охвате в его офисе и может определить, что правило одновременного звонка вызывает вызовы, чтобы перейти на мобильную голосовую почту Джо, когда его сетевое покрытие является плохим.</span><span class="sxs-lookup"><span data-stu-id="216b9-636">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="216b9-637">Майк является новым сотрудником в Contoso, и он присоединяется к новой команде, в которой все члены настроены для вызова группы, при включении в течение Skype для бизнеса Server 2015 г. администратор может настроить параметры группы по вызову команды, чтобы включить всех его новых членов команды, кроме того, администратор добавляет Майка в качестве члена группы вызова группы для каждого из членов его команды.</span><span class="sxs-lookup"><span data-stu-id="216b9-637">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="216b9-638">Практика обслуживания клиентов в отделе кадров в Contoso — предоставлять личную службу всем звонителям с первого звонка.</span><span class="sxs-lookup"><span data-stu-id="216b9-638">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="216b9-639">Учитывая, что все сотрудники отдела сидят очень близко друг к другу, для команды все телефоны звонят одновременно с командным вызовом.</span><span class="sxs-lookup"><span data-stu-id="216b9-639">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is disruptive for the team.</span></span> <span data-ttu-id="216b9-640">Чтобы обеспечить лучшую службу, не нарушая членов группы, администратор Skype для бизнеса Server 2015 г. воспользовался возможностями группового вызова.</span><span class="sxs-lookup"><span data-stu-id="216b9-640">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="216b9-641">Администратор добавляет всех сотрудников отдела в группу пикапов и передает в отдел номер группы пикапа.</span><span class="sxs-lookup"><span data-stu-id="216b9-641">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="216b9-642">Когда Саманта отсутствует на рабочем столе, Джо замечает звон телефона и продолжает отвечать на звонок со своего стола.</span><span class="sxs-lookup"><span data-stu-id="216b9-642">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-643">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-643">Requirements</span></span>

<span data-ttu-id="216b9-644">Средство SEFAUtil можно запускать только на компьютере, который является частью пула доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="216b9-644">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="216b9-645">На этом компьютере необходимо установить UCMA 3.0.</span><span class="sxs-lookup"><span data-stu-id="216b9-645">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="216b9-646">Чтобы запустить средство, в этом пуле должно быть создано новое надежное приложение с ИД приложения SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="216b9-646">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="216b9-647">Создание нового надежного приложения для средства SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="216b9-647">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="216b9-648">Средство SEFAUTil можно запускать только на компьютере, который является частью доверенного пула приложений.</span><span class="sxs-lookup"><span data-stu-id="216b9-648">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="216b9-649">При необходимости добавление пула в качестве нового доверенного пула приложений можно сделать с помощью Skype для бизнеса Server с помощью следующего команды:</span><span class="sxs-lookup"><span data-stu-id="216b9-649">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="216b9-650">UCMA 3.0 должна быть установлена на любом компьютере, который будет использоваться для запуска средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="216b9-650">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="216b9-651">Надежное приложение должно быть определено в топологии для средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="216b9-651">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="216b9-652">Чтобы определить SEFAUtil как новое надежное приложение, используйте Skype для бизнеса Server management Shell и выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="216b9-652">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="216b9-653">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="216b9-653">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="216b9-654">FQDN пула: FQDN сервера или пула, который будет принимать приложение SEFAUtil (обычно Skype для бизнеса сервер переднего > или пул).</span><span class="sxs-lookup"><span data-stu-id="216b9-654">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="216b9-655">FQDN регистратора пула: FQDN сервера Skype для бизнеса или пула, связанных с этим пулом приложений.</span><span class="sxs-lookup"><span data-stu-id="216b9-655">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="216b9-656">Сайт пула. ID сайта, на котором находится этот пул.</span><span class="sxs-lookup"><span data-stu-id="216b9-656">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="216b9-657">Необходимо включить изменения топологии.</span><span class="sxs-lookup"><span data-stu-id="216b9-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="216b9-658">Включение изменений топологии можно сделать с помощью Skype для бизнеса Server управленческой оболочки, исполнив следующий кодлет:</span><span class="sxs-lookup"><span data-stu-id="216b9-658">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="216b9-659">При необходимости установите на сервере Skype для бизнеса Server 2015 средства набора ресурсов, которые будут использоваться для запуска средства SEFAUtil (сервер должен быть частью доверенного пула приложений).</span><span class="sxs-lookup"><span data-stu-id="216b9-659">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="216b9-660">Убедитесь, что SEFAUtil работает правильно.</span><span class="sxs-lookup"><span data-stu-id="216b9-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="216b9-661">Для этого запустите средство из командной подсказки Windows с привилегиями администратора, чтобы отобразить параметры переададации вызовов пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="216b9-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="216b9-662">По умолчанию средство будет расположено в: "...\Program Files\Skype для бизнеса Server 2015\Reskit".</span><span class="sxs-lookup"><span data-stu-id="216b9-662">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="216b9-663">Чтобы отобразить параметры переададки вызовов пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="216b9-663">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="216b9-664">Необходимо отобразить параметры переададки вызовов пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-664">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="216b9-665">Групповой прием звонков</span><span class="sxs-lookup"><span data-stu-id="216b9-665">Group Call Pickup</span></span>

<span data-ttu-id="216b9-666">Для полного включения функции группового вызова Skype для бизнеса Server 2015 г. требуется дополнительная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="216b9-666">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="216b9-667">Прежде чем назначать группы пикапов пользователям, обратитесь к документации по продукту Групповой выбор вызовов для этапов планирования и развертывания этой возможности.</span><span class="sxs-lookup"><span data-stu-id="216b9-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-668">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-668">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="216b9-669">Отображение текущих Параметры</span><span class="sxs-lookup"><span data-stu-id="216b9-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="216b9-670">Следующая команда отображает обработку вызовов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-670">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="216b9-671">В этом примере **используется переключатель /server** для указания Skype для бизнеса Server для подключения.</span><span class="sxs-lookup"><span data-stu-id="216b9-671">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="216b9-672">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-672">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="216b9-673">Задай пункт назначения вызовов вперед/без ответа</span><span class="sxs-lookup"><span data-stu-id="216b9-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="216b9-674">В этом примере задайте пункт назначения вызовов вперед/без ответа и задержку звонка.</span><span class="sxs-lookup"><span data-stu-id="216b9-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="216b9-675">Здесь не предоставляется переключатель /server; SEFAUtil пытается автооткрыть Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="216b9-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="216b9-676">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="216b9-677">Включить немедленное переададение вызовов</span><span class="sxs-lookup"><span data-stu-id="216b9-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="216b9-678">В этом примере сразу же включается переададка вызовов другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="216b9-678">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="216b9-679">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="216b9-680">Отключение немедленной переададки вызовов</span><span class="sxs-lookup"><span data-stu-id="216b9-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="216b9-681">В этом примере немедленно отключает переададку вызовов.</span><span class="sxs-lookup"><span data-stu-id="216b9-681">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="216b9-682">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="216b9-683">Добавление пользователя в качестве делегата и настройка одновременного звонка делегатов</span><span class="sxs-lookup"><span data-stu-id="216b9-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="216b9-684">В этом примере пользователь добавляется в качестве делегата и настраивает одновременный звон делегатов.</span><span class="sxs-lookup"><span data-stu-id="216b9-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="216b9-685">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="216b9-686">Изменение правила одновременного звонка делегатов</span><span class="sxs-lookup"><span data-stu-id="216b9-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="216b9-687">В этом примере изменяется правило одновременного звонка, заданной в предыдущем примере, на правило задержки звонка.</span><span class="sxs-lookup"><span data-stu-id="216b9-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="216b9-688">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-688">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="216b9-689">Удаление делегата</span><span class="sxs-lookup"><span data-stu-id="216b9-689">Remove the Delegate</span></span>

<span data-ttu-id="216b9-690">В этом примере делегат удаляется.</span><span class="sxs-lookup"><span data-stu-id="216b9-690">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="216b9-691">При удалении последнего делегата звонок делегата автоматически отключен.</span><span class="sxs-lookup"><span data-stu-id="216b9-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="216b9-692">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="216b9-693">Добавление делегата и настройка правила Call-Forward для делегатов</span><span class="sxs-lookup"><span data-stu-id="216b9-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="216b9-694">В этом примере добавляется делегат и настраивается правило "Переадъемка для делегатов".</span><span class="sxs-lookup"><span data-stu-id="216b9-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="216b9-695">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-695">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="216b9-696">Включить одновременный звонок и установить номер назначения</span><span class="sxs-lookup"><span data-stu-id="216b9-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="216b9-697">В этом примере включается одновременный звон и устанавливается одновременный номер назначения звона.</span><span class="sxs-lookup"><span data-stu-id="216b9-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="216b9-698">Чтобы изменить одновременный номер назначения звона пользователя, который уже включен одновременным звоном, держите команду с переключателем /enablesimulring, в противном случае номер назначения не будет изменен.</span><span class="sxs-lookup"><span data-stu-id="216b9-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="216b9-699">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="216b9-700">Отключение одновременного звонка</span><span class="sxs-lookup"><span data-stu-id="216b9-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="216b9-701">В этом примере отключает одновременный звон.</span><span class="sxs-lookup"><span data-stu-id="216b9-701">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="216b9-702">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-702">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="216b9-703">Добавление участника группы для Team-Call и настройка одновременного звонка в группу Team-Call участников</span><span class="sxs-lookup"><span data-stu-id="216b9-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="216b9-704">В этом примере добавляется член группы в группу вызовов пользователя и включается одновременный звон в группу вызовов.</span><span class="sxs-lookup"><span data-stu-id="216b9-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="216b9-705">Добавление участника в группу вызовов пользователя автоматически переключает синхронный звон сеттиг пользователей на одновременный звонок его группы вызова группы.</span><span class="sxs-lookup"><span data-stu-id="216b9-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simultaneous ring his team-call group.</span></span>

 <span data-ttu-id="216b9-706">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-706">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="216b9-707">Удаление участника из Team-Call группы</span><span class="sxs-lookup"><span data-stu-id="216b9-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="216b9-708">В этом примере удаляется член группы вызова группы пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-708">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="216b9-709">Если удаляемый член является единственным членом группы вызовов, одновременное звон в группу вызовов будет автоматически отключен.</span><span class="sxs-lookup"><span data-stu-id="216b9-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="216b9-710">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="216b9-711">Установите задержанное кольцо в группу Team-Call</span><span class="sxs-lookup"><span data-stu-id="216b9-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="216b9-712">В этом примере отложенное кольцо изменяется в параметр времени группового вызова группы.</span><span class="sxs-lookup"><span data-stu-id="216b9-712">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="216b9-713">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-713">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="216b9-714">Включить Team-Call</span><span class="sxs-lookup"><span data-stu-id="216b9-714">Enable Team-Call</span></span>

<span data-ttu-id="216b9-715">В этом примере включается командный вызов для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-715">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="216b9-716">Если в группе командных зовов пользователя нет участников, вызов группы не будет включен.</span><span class="sxs-lookup"><span data-stu-id="216b9-716">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="216b9-717">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-717">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="216b9-718">Отключение Team-Call</span><span class="sxs-lookup"><span data-stu-id="216b9-718">Disable Team-Call</span></span>

<span data-ttu-id="216b9-719">В этом примере отключен вызов группы для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-719">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="216b9-720">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="216b9-721">Включить групповую группу вызова и назначить группу пикапа пользователю</span><span class="sxs-lookup"><span data-stu-id="216b9-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="216b9-722">В этом примере группа пикапов назначается пользователю и включает групповую группу вызова.</span><span class="sxs-lookup"><span data-stu-id="216b9-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="216b9-723">**Вывести**</span><span class="sxs-lookup"><span data-stu-id="216b9-723">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="216b9-724">Отключение группового вызова</span><span class="sxs-lookup"><span data-stu-id="216b9-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="216b9-725">В этом примере отключает групповой вызов для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-725">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="216b9-726">При отключении группового вызова для пользователя номер группы, назначенный пользователю, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="216b9-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="216b9-727">Если впоследствии необходимо повторно включить групповой вызов для этого пользователя, необходимо назначить номер группы снова с помощью переключателя /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="216b9-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="216b9-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="216b9-728">SYSPrep.ps1</span></span>
<span data-ttu-id="216b9-729"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-729"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="216b9-730">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-730">Description</span></span>

<span data-ttu-id="216b9-731">SYSPrep.ps1 — это Windows PowerShell, который установит следующие Skype для бизнеса Server 2015 г. на компьютере Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="216b9-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="216b9-732">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="216b9-732">Microsoft .NET Framework 4.5</span></span>

- <span data-ttu-id="216b9-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="216b9-733">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="216b9-734">Windows PowerShell версии 3.0</span><span class="sxs-lookup"><span data-stu-id="216b9-734">Windows PowerShell version 3.0</span></span>

- <span data-ttu-id="216b9-735">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="216b9-735">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="216b9-736">Обновления информационного сервера Интернета</span><span class="sxs-lookup"><span data-stu-id="216b9-736">Internet Information Server Updates</span></span>

- <span data-ttu-id="216b9-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="216b9-737">Windows Identity Foundation</span></span>

- <span data-ttu-id="216b9-738">Skype для бизнеса Server 2015 Core files</span><span class="sxs-lookup"><span data-stu-id="216b9-738">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="216b9-739">Хотя имя скрипта похоже на средство подготовки системы для операционных систем Microsoft Windows, они отличаются.</span><span class="sxs-lookup"><span data-stu-id="216b9-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="216b9-740">Этот скрипт установит только необходимые условия для Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-740">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="216b9-741">После установки этих необходимых Windows SYSPrep можно использовать для создания изображения сервера.</span><span class="sxs-lookup"><span data-stu-id="216b9-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-742">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-742">Requirements</span></span>

<span data-ttu-id="216b9-743">Перед запуском SYSPrep.ps1 необходимо скопировать необходимые файлы в локализованную папку на компьютере операционной системы Windows Server 2008 **(например, D:\Setup).**</span><span class="sxs-lookup"><span data-stu-id="216b9-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="216b9-744">Эта папка также должна включать копию Skype для бизнеса Server 2015 года, в частности **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="216b9-744">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="216b9-745">Необходимые файлы можно загрузить из следующих местоположений:</span><span class="sxs-lookup"><span data-stu-id="216b9-745">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="216b9-746">**Предварительное условие**</span><span class="sxs-lookup"><span data-stu-id="216b9-746">**Prerequisite**</span></span>                                | <span data-ttu-id="216b9-747">**Location**</span><span class="sxs-lookup"><span data-stu-id="216b9-747">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="216b9-748">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="216b9-748">Microsoft .NET Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="216b9-749">Microsoft SQL Server Express R2 2008</span><span class="sxs-lookup"><span data-stu-id="216b9-749">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="216b9-750">Windows PowerShell версии 3.0</span><span class="sxs-lookup"><span data-stu-id="216b9-750">Windows PowerShell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="216b9-751">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="216b9-751">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="216b9-752">Обновления информационного сервера Интернета</span><span class="sxs-lookup"><span data-stu-id="216b9-752">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="216b9-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="216b9-753">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="216b9-754">Skype для бизнеса Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="216b9-754">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="216b9-755">Копирование из Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-755">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="216b9-756">Параметр</span><span class="sxs-lookup"><span data-stu-id="216b9-756">Parameter</span></span>

<span data-ttu-id="216b9-757">Параметр **-SetupFolder** принимает в качестве аргумента расположение каталога необходимых файлов</span><span class="sxs-lookup"><span data-stu-id="216b9-757">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-758">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-758">Examples</span></span>

<span data-ttu-id="216b9-759">Чтобы запустить SYSPrep.ps1 и установить необходимые Skype для бизнеса Server 2015 г., запустите следующую команду из командной подсказки:</span><span class="sxs-lookup"><span data-stu-id="216b9-759">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="216b9-760">Миграция неназвных объявлений номеров</span><span class="sxs-lookup"><span data-stu-id="216b9-760">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="216b9-761"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-761"><a name="UNAM"> </a></span></span>

<span data-ttu-id="216b9-762">Средство миграции ненаправленных объявлений номеров позволяет администратору Skype для бизнеса Server 2015 года переместить конфигурацию ненаправленных номеров, которая обслужяется приложением объявления из источника Skype для бизнеса Server или Пула в пункт назначения Skype для бизнеса Server или пул.</span><span class="sxs-lookup"><span data-stu-id="216b9-762">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-763">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-763">Description</span></span>

<span data-ttu-id="216b9-764">Средство миграции неназвных объявлений номеров — это сценарий Windows PowerShell, который перемещает конфигурацию ненанаписаных номеров, служив с помощью приложения-объявления исходных серверов или пула, на другой сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="216b9-764">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="216b9-765">При выполнении сценарий миграции без присвоения номеров выполнит следующие операции:</span><span class="sxs-lookup"><span data-stu-id="216b9-765">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="216b9-766">Перемещение всех аудиофайлов, используемых неназваными номерами приложения-объявления, хранимого на сервере источника или пуле, в хранилище файлов конечного сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="216b9-766">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="216b9-767">Аудиофайлы удаляются из пула исходных данных после их копирования в пул назначения.</span><span class="sxs-lookup"><span data-stu-id="216b9-767">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="216b9-768">Перемещение всех ненаправленных номеров, настроенных для приложения-объявления, на сервере или пуле источника, на сервер назначения или пул.</span><span class="sxs-lookup"><span data-stu-id="216b9-768">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="216b9-769">Перенаправление всех ненаправленных диапазонов номеров, которые обслуживало приложение объявления, на сервере источника или пуле, на сервер назначения или пул.</span><span class="sxs-lookup"><span data-stu-id="216b9-769">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="216b9-770">После успешного запуска скрипта все ненаправленные диапазоны номеров, которые были обслужимы приложением объявлений, на сервере или пуле исходных источников, теперь будут обслужимы с той же конфигурацией сервером назначения или пулом.</span><span class="sxs-lookup"><span data-stu-id="216b9-770">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-771">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-771">Output</span></span>

<span data-ttu-id="216b9-772">Сценарий **Move-CsAnnouncementConfiguration** указывает в окне Skype для бизнеса Server Management Shell, откуда выполняется успешность или сбой операции миграции.</span><span class="sxs-lookup"><span data-stu-id="216b9-772">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="216b9-773">Если выполнение операции прерывается из-за какой-либо ошибки, ненаправленные диапазоны номеров, успешно перемещенные в пункт назначения, останутся в пункте назначения в операционной форме, а остальные ненаправленные диапазоны номеров, которые будут перенесены, останутся в источнике, а также в операционной форме.</span><span class="sxs-lookup"><span data-stu-id="216b9-773">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="216b9-774">Чтобы полностью перенести остальную конфигурацию, повторяем сценарий после устранения ошибки.</span><span class="sxs-lookup"><span data-stu-id="216b9-774">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="216b9-775">Назначение</span><span class="sxs-lookup"><span data-stu-id="216b9-775">Purpose</span></span>

<span data-ttu-id="216b9-776">Сценарий миграции без присвоения номеров можно использовать в следующих трех сценариях:</span><span class="sxs-lookup"><span data-stu-id="216b9-776">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="216b9-777">**Перенос параметров конфигурации в новую версию Skype для бизнеса Server:** Contoso находится в процессе миграции в Skype для бизнеса Server 2015 г., и в рамках процесса миграции администратор Skype для бизнеса Server хотел бы перенести конфигурацию ненаправленных номеров, обслужив приложением объявлений, из развертывания Lync Server 2013 в новое развертывание Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-777">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="216b9-778">Чтобы переместить параметры конфигурации, администратор Skype для бизнеса Server использует средство миграции ненаправленных объявлений о количестве.</span><span class="sxs-lookup"><span data-stu-id="216b9-778">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="216b9-779">**Откат развертывания с Skype для бизнеса Server 2015 г. до Lync Server 2013:** Из-за непредвиденных факторов Contoso должна откатить миграцию в новое развертывание Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-779">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="216b9-780">Чтобы свести к минимуму нарушения работы службы, администратор Skype для бизнеса Server использует средство миграции ненаправленных объявлений о количестве для отката конфигурации с развертывания Skype для бизнеса Server 2015 г. в развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="216b9-780">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="216b9-781">**Перемещение данных между развертываниями:** Contoso находится в процессе замены всех серверов одного пула более новыми серверами.</span><span class="sxs-lookup"><span data-stu-id="216b9-781">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="216b9-782">Их стратегия заключается в развертывании нового пула Skype для бизнеса Server 2015 г., перемещение всех данных из старого в новый пул, а затем обесценить старый пул.</span><span class="sxs-lookup"><span data-stu-id="216b9-782">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="216b9-783">После развертывания нового пула для переноса конфигурации из старого пула в новый используется средство миграции неназвинных объявлений номеров.</span><span class="sxs-lookup"><span data-stu-id="216b9-783">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="216b9-784">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-784">Requirements</span></span>

<span data-ttu-id="216b9-785">Основные требования, необходимые для успешного запуска инструмента:</span><span class="sxs-lookup"><span data-stu-id="216b9-785">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="216b9-786">Сценарий должен запускаться с компьютера, на Skype для бизнеса Server установленной оболочки управления.</span><span class="sxs-lookup"><span data-stu-id="216b9-786">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="216b9-787">Приложение объявления должно быть успешно развернуто в источнике и Skype для бизнеса серверах или пулах.</span><span class="sxs-lookup"><span data-stu-id="216b9-787">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="216b9-788">Move-CsAnnouncementConfiguration сценарий</span><span class="sxs-lookup"><span data-stu-id="216b9-788">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="216b9-789">Сценарий Move-CsAnnouncementConfiguration требует двух параметров, описанных в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="216b9-789">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration параметры.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="216b9-791">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-791">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="216b9-792">Перемещение конфигурации неназланных объявлений о количестве из пула Lync Server 2013 в пул Skype для бизнеса Server 2015 г.</span><span class="sxs-lookup"><span data-stu-id="216b9-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="216b9-793">В этом примере ненаправленные объявления номеров перемещаются из пула исходных данных (Lync Server 2013) в пул назначения (Skype для бизнеса Server 2015).</span><span class="sxs-lookup"><span data-stu-id="216b9-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="216b9-794">Перемещение конфигурации неназланных номеров из пула Skype для бизнеса Server 2015 г. в пул Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="216b9-794">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="216b9-795">В этом примере ненаправленные объявления номеров перемещаются из пула исходных номеров (Skype для бизнеса Server 2015 г.) в пул назначения (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="216b9-795">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="216b9-796">Данные веб-конфи</span><span class="sxs-lookup"><span data-stu-id="216b9-796">Web Conf Data</span></span>
<span data-ttu-id="216b9-797"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="216b9-797"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="216b9-798">Средство обработки данных веб-конференций позволяет администратору программного обеспечения Skype для бизнеса Server связи 2015 года иметь больше контроля над данными, связанными с веб-конференциями организатора.</span><span class="sxs-lookup"><span data-stu-id="216b9-798">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="216b9-799">Сценарии включают возможность удаления данных собраний определенного пользователя на основе критериев штампа времени.</span><span class="sxs-lookup"><span data-stu-id="216b9-799">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="216b9-800">Описание</span><span class="sxs-lookup"><span data-stu-id="216b9-800">Description</span></span>

<span data-ttu-id="216b9-801">Этот инструмент позволяет администратору выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="216b9-801">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="216b9-802">Поиск всех данных веб-конференций, связанных с одним пользователем.</span><span class="sxs-lookup"><span data-stu-id="216b9-802">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="216b9-803">Удаление всех данных веб-конференций, связанных с одним пользователем.</span><span class="sxs-lookup"><span data-stu-id="216b9-803">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="216b9-804">Удаление всех данных веб-конференций, связанных с одним пользователем, который старше определенной даты.</span><span class="sxs-lookup"><span data-stu-id="216b9-804">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="216b9-805">Перемещение всех данных веб-конференций, связанных с одним пользователем при перемещении этого пользователя из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="216b9-805">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="216b9-806">Средства набора ресурсов для Lync Server 2010 поддерживали перемещение всех данных веб-конференций, связанных с одним пользователем при перемещении этого пользователя из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="216b9-806">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="216b9-807">Эта функция теперь отстает от этого средства в пользу **параметра MoveConferenceData.**</span><span class="sxs-lookup"><span data-stu-id="216b9-807">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="216b9-808">Сведения об этом параметре см. в [комлете Move-CsUser.](/powershell/module/skype/move-csuser?)</span><span class="sxs-lookup"><span data-stu-id="216b9-808">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser?) cmdlet.</span></span>

<span data-ttu-id="216b9-809">Средство удаляет данные собраний только для неактивных собраний.</span><span class="sxs-lookup"><span data-stu-id="216b9-809">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="216b9-810">Активные собрания (или собрания в сеансах) не могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="216b9-810">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="216b9-811">Этот инструмент должен запускаться с компьютера, который находится в том же пуле, что и целевой пользователь.</span><span class="sxs-lookup"><span data-stu-id="216b9-811">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="216b9-812">Пользователь, чьими данными контента собраний управляется с помощью этого средства, должен быть у себя в одном пуле пользователей.</span><span class="sxs-lookup"><span data-stu-id="216b9-812">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="216b9-813">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="216b9-813">Output</span></span>

<span data-ttu-id="216b9-814">Этот инструмент выводит результаты каждой из операций:</span><span class="sxs-lookup"><span data-stu-id="216b9-814">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="216b9-815">Если выполняется запрос, средство выводит список всех неактивных папок данных собраний, которые имеют этого пользователя в качестве организатора.</span><span class="sxs-lookup"><span data-stu-id="216b9-815">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="216b9-816">Если выполняется удаление, средство выводит список всех папок данных собраний, данные которых будут удалены.</span><span class="sxs-lookup"><span data-stu-id="216b9-816">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="216b9-817">Requirements</span><span class="sxs-lookup"><span data-stu-id="216b9-817">Requirements</span></span>

<span data-ttu-id="216b9-818">Этот инструмент необходимо запустить в том же пуле, где в настоящее время находится организатор.</span><span class="sxs-lookup"><span data-stu-id="216b9-818">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="216b9-819">Этот инструмент должен запускаться с использованием привилегий администратора с доступом к хранилище файлов контента.</span><span class="sxs-lookup"><span data-stu-id="216b9-819">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="216b9-820">Примеры</span><span class="sxs-lookup"><span data-stu-id="216b9-820">Examples</span></span>

<span data-ttu-id="216b9-821">В следующей таблице описываются параметры, некоторые из которых используются в примерах.</span><span class="sxs-lookup"><span data-stu-id="216b9-821">The following table describes the parameters, some of which are used in the examples.</span></span>

![Параметры средства данных Web Conf.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="216b9-823">В предыдущем примере показано, как будет работать команда запроса.</span><span class="sxs-lookup"><span data-stu-id="216b9-823">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="216b9-824">Выход такой команды будет списком всех папок контента собраний, которые будут затронуты этим средством.</span><span class="sxs-lookup"><span data-stu-id="216b9-824">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="216b9-825">Предыдущий пример команды удаления.</span><span class="sxs-lookup"><span data-stu-id="216b9-825">The preceding is an example of a delete command.</span></span> <span data-ttu-id="216b9-826">Команда удаления удаляет все неактивные папки собраний у этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="216b9-826">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="216b9-827">Сводка</span><span class="sxs-lookup"><span data-stu-id="216b9-827">Summary</span></span>

<span data-ttu-id="216b9-828">Этот инструмент может быть ценным ресурсом для администраторов, которым требуется более точный контроль над данными собраний конференций.</span><span class="sxs-lookup"><span data-stu-id="216b9-828">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
