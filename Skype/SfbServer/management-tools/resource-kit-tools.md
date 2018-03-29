---
title: Документация по инструментам Skype для бизнеса Server 2015 Resource Kit
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: В этом разделе описываются средства в Скайп Business Server 2015 для набора ресурсов для, включая назначение каждого средства и примеры его использования. Скайп для набора ресурсов 2015 Business Server позволяет упростить выполнять рутинные задачи для ИТ-администраторам, развертывания и управления Скайп для Business Server 2015. Например средство веб-конференции данных можно использовать для легко управлять данные, которые отправлены пользователями во время собрания по сети. Средство SEFAUtil можно использовать для настройки вызова делегата, переадресация и ответы на для пользователей. Мы рекомендуем использовать эти средства для более эффективного управления Скайп для Business Server 2015 ИТ-администраторов.
ms.openlocfilehash: 8367400ea7730eabbd2686c3bb2b7c16cdf9a1f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="225c5-107">Документация по инструментам Skype для бизнеса Server 2015 Resource Kit</span><span class="sxs-lookup"><span data-stu-id="225c5-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>
 
<span data-ttu-id="225c5-108">В этом разделе описываются средства в Скайп Business Server 2015 для набора ресурсов для, включая назначение каждого средства и примеры его использования.</span><span class="sxs-lookup"><span data-stu-id="225c5-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="225c5-109">Скайп для набора ресурсов 2015 Business Server позволяет упростить выполнять рутинные задачи для ИТ-администраторам, развертывания и управления Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="225c5-110">Например, инструмент **Web Conf Data** упрощает управление данными, которые отправляют пользователи во время собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="225c5-111">А при помощи **SEFAUtil** можно настроить переадресацию звонков делегатам и ответ на них для пользователей.</span><span class="sxs-lookup"><span data-stu-id="225c5-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="225c5-112">Мы рекомендуем использовать эти средства для более эффективного управления Скайп для Business Server 2015 ИТ-администраторов.</span><span class="sxs-lookup"><span data-stu-id="225c5-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>
  
## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="225c5-113">Установка средств из набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="225c5-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="225c5-114">Чтобы установить Скайп для набора ресурсов Business Server 2015, загрузите [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) из центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="225c5-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>
  
<span data-ttu-id="225c5-p103">Чтобы выполнить простую установку, запустите файл **OCSResKit.msi**. MSI-файл установит все средства в следующую папку: **%Program Files%\Skype for Business Server 2015\ResKit**. Инструменты, представляющие собой автономные исполняемые файлы, находятся непосредственно в этой папке. Инструменты, имеющие дополнительные файлы, находятся в отдельных вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="225c5-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>
  
## <a name="supported-environments"></a><span data-ttu-id="225c5-119">Поддерживаемые среды</span><span class="sxs-lookup"><span data-stu-id="225c5-119">Supported Environments</span></span>

<span data-ttu-id="225c5-120">Скайп для набора ресурсов 2015 Business Server должны быть установлены на сервере, который соответствует требованиям для Скайп для Business Server 2015, обычно на одном используется для запуска Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>
  
## <a name="resource-kit-tools-overview"></a><span data-ttu-id="225c5-121">Обзор средств из набора ресурсов</span><span class="sxs-lookup"><span data-stu-id="225c5-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="225c5-122">Ниже приведен список средств, представленных в Скайп для набора ресурсов 2015 Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="225c5-123">Описание каждого средства, включая требования и примеры использования, можно найти в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="225c5-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>
  
- [<span data-ttu-id="225c5-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="225c5-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)
    
- [<span data-ttu-id="225c5-125">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="225c5-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)
    
- [<span data-ttu-id="225c5-126">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="225c5-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)
    
- [<span data-ttu-id="225c5-127">Счетчик парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="225c5-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)
    
- [<span data-ttu-id="225c5-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="225c5-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)
    
- [<span data-ttu-id="225c5-129">Импорт данных службы хранилища</span><span class="sxs-lookup"><span data-stu-id="225c5-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)
    
- [<span data-ttu-id="225c5-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="225c5-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)
    
- [<span data-ttu-id="225c5-131">Консоль поиска пользователей</span><span class="sxs-lookup"><span data-stu-id="225c5-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)
    
- [<span data-ttu-id="225c5-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="225c5-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)
    
- [<span data-ttu-id="225c5-133">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="225c5-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)
    
- [<span data-ttu-id="225c5-134">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="225c5-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)
    
- [<span data-ttu-id="225c5-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="225c5-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)
    
- [<span data-ttu-id="225c5-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="225c5-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)
    
- [<span data-ttu-id="225c5-137">Перенос оповещений о неназначенных номерах</span><span class="sxs-lookup"><span data-stu-id="225c5-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)
    
- [<span data-ttu-id="225c5-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="225c5-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)
    
## <a name="absconfig"></a><span data-ttu-id="225c5-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="225c5-139">ABSConfig</span></span>
<span data-ttu-id="225c5-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-140"></span></span>

<span data-ttu-id="225c5-141">Средство конфигурации службы адресной книги (ABSConfig) — это средство администрирования, помогающих администраторам настроить конфигурацию службы адресной книги в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="225c5-142">Это средство также позволяет Скайп для администраторов Business Server 2015 для восстановления службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="225c5-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-143">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-143">Description</span></span>

<span data-ttu-id="225c5-144">ABSConfig является приложением графический пользовательский интерфейс, который позволяет администраторам настраивать атрибуты доменных служб Active Directory, которые связаны с службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="225c5-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>
  
<span data-ttu-id="225c5-145">Основные сценарии использования этого средства:</span><span class="sxs-lookup"><span data-stu-id="225c5-145">The primary scenarios for the tool are the following:</span></span>
  
- <span data-ttu-id="225c5-146">Чтобы разрешить администраторам сопоставление атрибутов в доменных службах Active Directory в атрибуты для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="225c5-147">позволяет администраторам указывать, что атрибут доменных служб Active Directory должен быть включен в файлы службы адресной книги или исключен из них;</span><span class="sxs-lookup"><span data-stu-id="225c5-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>
    
- <span data-ttu-id="225c5-148">позволяет администраторам восстанавливать параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="225c5-148">To enable administrators to restore default Address Book Service settings.</span></span>
    
<span data-ttu-id="225c5-149">Средство ABSConfig можно запустить с помощью файла absConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="225c5-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="225c5-150">Средство открывается на вкладке **Настройка атрибутов** . Эта таблица имеет настроек для сопоставления доменных служб Active Directory атрибуты полей атрибута для Скайп для Business Server 2015, а также для определения пользователей, которые включаются или исключаются в файлов службы адресной книги в зависимости от конкретного атрибута фильтры.</span><span class="sxs-lookup"><span data-stu-id="225c5-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="225c5-151">Также можно настроить значение номера телефона, которое необходимо включить в файл адресной книги.</span><span class="sxs-lookup"><span data-stu-id="225c5-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="225c5-152">Кнопка **Восстановить значения по умолчанию** позволяет администраторам восстановить параметры службы адресной книги по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="225c5-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>
  
### <a name="output"></a><span data-ttu-id="225c5-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-153">Output</span></span>

<span data-ttu-id="225c5-154">Средство ABSConfig сохраняет конфигурацию службы адресной книги в базе данных.</span><span class="sxs-lookup"><span data-stu-id="225c5-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>
  
```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="225c5-155">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-155">Purpose</span></span>

<span data-ttu-id="225c5-156">ABSConfig позволяет быстро и легко настроить Скайп для службы Business Server 2015 адресной книги.</span><span class="sxs-lookup"><span data-stu-id="225c5-156">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="225c5-157">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-157">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="225c5-158">Компьютер</span><span class="sxs-lookup"><span data-stu-id="225c5-158">Computer</span></span>

<span data-ttu-id="225c5-159">ABSConfig может выполняться только с компьютера, присоединенный к домену, который имеет Скайп для Business Server 2015 установлены.</span><span class="sxs-lookup"><span data-stu-id="225c5-159">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="225c5-160">В случае Скайп для 2015 сервера Business, Enterprise Edition этой программы может выполняться на любой серверов переднего плана, на которых включена во время установки службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="225c5-160">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>
  
#### <a name="network"></a><span data-ttu-id="225c5-161">Сеть</span><span class="sxs-lookup"><span data-stu-id="225c5-161">Network</span></span>

<span data-ttu-id="225c5-162">Компьютер должен иметь возможность подключения к интерфейсному пулу и внутренней базе данных.</span><span class="sxs-lookup"><span data-stu-id="225c5-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>
  
#### <a name="software"></a><span data-ttu-id="225c5-163">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="225c5-163">Software</span></span>

<span data-ttu-id="225c5-164">Перед запуском средства ABSConfig необходимо установить перечисленные ниже программные компоненты.</span><span class="sxs-lookup"><span data-stu-id="225c5-164">The following software components must be installed before running the ABSConfig tool:</span></span>
  
- <span data-ttu-id="225c5-165">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="225c5-165">Skype for Business Server 2015</span></span>
    
#### <a name="users"></a><span data-ttu-id="225c5-166">Пользователи</span><span class="sxs-lookup"><span data-stu-id="225c5-166">Users</span></span>

<span data-ttu-id="225c5-167">Администраторы, которые имеют разрешения, необходимые для обновления Скайп для развертывания Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-167">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-168">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-168">Examples</span></span>

<span data-ttu-id="225c5-p108">Средство ABSConfig можно запустить, введя в командной строке команду **ABSConfig.exe**. Ниже показан пользовательский интерфейс средства ABSConfig.</span><span class="sxs-lookup"><span data-stu-id="225c5-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>
  
![Средство ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)
  
### <a name="summary"></a><span data-ttu-id="225c5-172">Заключение</span><span class="sxs-lookup"><span data-stu-id="225c5-172">Summary</span></span>

<span data-ttu-id="225c5-173">Средство ABSConfig предоставляет администраторам быстрый и простой в использовании средства для настройки Скайп для службы Business Server 2015 адресной книги.</span><span class="sxs-lookup"><span data-stu-id="225c5-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>
  
## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="225c5-174">Монитор службы политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="225c5-174">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="225c5-175"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-175"></span></span>

<span data-ttu-id="225c5-176">Монитор службы политики пропускной способности позволяет администраторам просматривать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="225c5-176">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>
  
1. <span data-ttu-id="225c5-177">Все настроенные Скайп для служб Business Server 2015 полосы пропускания (проверка подлинности и основных) в топологии</span><span class="sxs-lookup"><span data-stu-id="225c5-177">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>
    
2. <span data-ttu-id="225c5-178">соединения, которые каждая служба устанавливает с другими службами политики пропускной способности и с пограничными серверами;</span><span class="sxs-lookup"><span data-stu-id="225c5-178">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>
    
3. <span data-ttu-id="225c5-179">все каналы, настроенные в документе конфигурации сети, и сведения об использовании пропускной способности в реальном времени, сообщаемые каждой службой политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="225c5-179">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>
    
### <a name="description"></a><span data-ttu-id="225c5-180">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-180">Description</span></span>

<span data-ttu-id="225c5-p109">Монитор службы политики пропускной способности реализован в виде приложения с графическим пользовательским интерфейсом. Чтобы запустить средство, администраторам необходимо выполнить файл PDPMonUI.exe.</span><span class="sxs-lookup"><span data-stu-id="225c5-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>
  
<span data-ttu-id="225c5-p110">При запуске средства оно пытается обнаружить все службы политики пропускной способности в топологии. После начального обновления данных область в левой части окна заполняется списком служб, сгруппированным по кластерам, к которым они относятся.</span><span class="sxs-lookup"><span data-stu-id="225c5-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>
  
<span data-ttu-id="225c5-p111">Когда администратор выбирает определенную службу политики пропускной способности, в области справа выводятся сведения о ней. Эта область имеет две основные вкладки.</span><span class="sxs-lookup"><span data-stu-id="225c5-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>
  
#### <a name="machine-info-tab"></a><span data-ttu-id="225c5-187">Вкладка Machine Info</span><span class="sxs-lookup"><span data-stu-id="225c5-187">Machine Info Tab</span></span>

<span data-ttu-id="225c5-188">На вкладке **Machine Info** (Сведения о компьютере) выводятся подробные сведения о выбранной службе политики пропускной способности, а также список соединений, установленных этой службой с другими службами, и их состояний.</span><span class="sxs-lookup"><span data-stu-id="225c5-188">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>
  
#### <a name="topology-info-tab"></a><span data-ttu-id="225c5-189">Вкладка Topology Info</span><span class="sxs-lookup"><span data-stu-id="225c5-189">Topology Info Tab</span></span>

<span data-ttu-id="225c5-p112">На вкладке **Topology Info** (Сведения о топологии) показан список всех каналов, настроенных в параметрах конфигурации сети. Для каждого канала показана пропускная способность звука и видео. Кроме того, показана текущая используемая пропускная способность в Кбит/с и в процентах от общей пропускной способности. Для выделения каналов, пропускная способность которых используется почти максимально, в средстве применяется цветовая кодировка. Это позволяет администраторам быстро определять такие каналы.</span><span class="sxs-lookup"><span data-stu-id="225c5-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="225c5-194">Если средство монитор службы политики пропускной способности произойдет сбой при подключении к любой из настроенные службы политики пропускной способности, сведения в вкладки **Сведения о топологии** и **Сведения о компьютере** не появится.</span><span class="sxs-lookup"><span data-stu-id="225c5-194">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="225c5-195">Однако также возможна ситуация, когда средству изначально удается подключиться к службе, но затем это соединение оказывается разорванным.</span><span class="sxs-lookup"><span data-stu-id="225c5-195">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="225c5-196">В таких случаях администраторы будут видеть устаревшие данные.</span><span class="sxs-lookup"><span data-stu-id="225c5-196">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="225c5-197">На каждой вкладке есть метка времени **Last Updated** (Последнее обновление), с помощью которой администраторы могут узнать, когда в последний раз обновлялись данные для определенной службы политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="225c5-197">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>
  
### <a name="output"></a><span data-ttu-id="225c5-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-198">Output</span></span>

<span data-ttu-id="225c5-199">Вывод данных через командную строку не используется. Данные программы выводятся в основном графическом интерфейсе пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-199">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>
  
### <a name="purpose"></a><span data-ttu-id="225c5-200">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-200">Purpose</span></span>

<span data-ttu-id="225c5-p114">Монитор службы политики пропускной способности позволяет администраторам просматривать состояние каждой службы политики пропускной способности, определенной в топологии. Кроме того, администраторы могут просматривать сведения об использовании пропускной способности в реальном времени для всех каналов, определенных в документе конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="225c5-203">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-203">Requirements</span></span>

<span data-ttu-id="225c5-204">Средство монитор службы политики пропускной способности необходимо выполнять на компьютере, который является частью Скайп для топологии Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-204">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>
  
### <a name="summary"></a><span data-ttu-id="225c5-205">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-205">Summary</span></span>

<span data-ttu-id="225c5-206">Монитор службы пропускной способности может быть ценным ресурсом для администраторов, позволяя им наблюдать за состоянием всех служб политики пропускной способности в топологии и, что еще более важно, получать сведения об использовании пропускной способности в реальном времени для каналов, определенных в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-206">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>
  
## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="225c5-207">Анализатор использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="225c5-207">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="225c5-208"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-208"></span></span>

<span data-ttu-id="225c5-p115">Анализатор использования полосы пропускания — это средство, которое создает отчеты о различных аспектах использования полосы пропускания каналов глобальной сети конечными точками объединенных коммуникаций в корпоративной сети. Эти отчеты можно использовать для анализа текущей схемы использования полосы пропускания, а также при планировании емкости полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="225c5-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-211">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-211">Description</span></span>

<span data-ttu-id="225c5-p116">Анализатор использования полосы пропускания реализован в виде приложения с графическим пользовательским интерфейсом. Это средство создает отчеты об использовании полосы пропускания аудиоданных в сети и помогает при планировании ресурсов. Оно также позволяет просматривать полосу пропускания, назначенную различным каналам.</span><span class="sxs-lookup"><span data-stu-id="225c5-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>
  
### <a name="output"></a><span data-ttu-id="225c5-215">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-215">Output</span></span>

<span data-ttu-id="225c5-216">Анализатор использования пропускной способности предоставляет графическое изображение полосы пропускания аудиоданных и степени ее использования для всех каналов глобальной сети, настроенных в системе.</span><span class="sxs-lookup"><span data-stu-id="225c5-216">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="225c5-217">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-217">Purpose</span></span>

<span data-ttu-id="225c5-218">В голосовой и видеосвязи развертывания очень важно для контроля и понять тенденции использования пропускной способности трафика мультимедиа в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-218">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="225c5-219">Анализатор использования полосы пропускания позволяет администраторам решать эту задачу.</span><span class="sxs-lookup"><span data-stu-id="225c5-219">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="225c5-220">Это средство предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="225c5-220">This tool does the following:</span></span>
  
- <span data-ttu-id="225c5-221">создает отчеты по использованию звуковых каналов в сети;</span><span class="sxs-lookup"><span data-stu-id="225c5-221">Generates specific reports for audio utilization across the network</span></span>
    
- <span data-ttu-id="225c5-222">позволяет более эффективно планировать емкость и распределять полосы пропускания, назначенные различным каналам.</span><span class="sxs-lookup"><span data-stu-id="225c5-222">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>
    
<span data-ttu-id="225c5-223">Анализатор пропускной способности позволяет создавать следующие графические отчеты о полосе пропускания и степени ее загрузки:</span><span class="sxs-lookup"><span data-stu-id="225c5-223">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>
  
- <span data-ttu-id="225c5-224">для всех каналов глобальной сети в корпоративной сети;</span><span class="sxs-lookup"><span data-stu-id="225c5-224">All the WAN links in the enterprise network</span></span>
    
- <span data-ttu-id="225c5-225">для выбранных каналов глобальной сети;</span><span class="sxs-lookup"><span data-stu-id="225c5-225">Filtered by selected WAN links that have been chosen</span></span>
    
- <span data-ttu-id="225c5-226">для каналов глобальной сети, емкость которых превышена;</span><span class="sxs-lookup"><span data-stu-id="225c5-226">Filtered by WAN links that have exceeded link capacity</span></span>
    
- <span data-ttu-id="225c5-227">для каналов глобальной сети, полоса пропускания которых используется недостаточно;</span><span class="sxs-lookup"><span data-stu-id="225c5-227">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>
    
- <span data-ttu-id="225c5-228">для каналов глобальной сети, использование которых достигает критического уровня (то есть превышает 90 % полосы пропускания канала глобальной сети);</span><span class="sxs-lookup"><span data-stu-id="225c5-228">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>
    
- <span data-ttu-id="225c5-229">для каналов глобальной сети, отфильтрованных по типу: каналы между сетевыми сайтами, каналы между областями и каналы внутри сайта;</span><span class="sxs-lookup"><span data-stu-id="225c5-229">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>
    
- <span data-ttu-id="225c5-230">с фильтрацией по области сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-230">Filtered by network region</span></span>
    
#### <a name="applications"></a><span data-ttu-id="225c5-231">Приложения</span><span class="sxs-lookup"><span data-stu-id="225c5-231">Applications</span></span>

<span data-ttu-id="225c5-232">Анализатор использования полосы пропускания включает следующие два приложения (средства).</span><span class="sxs-lookup"><span data-stu-id="225c5-232">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>
  
- <span data-ttu-id="225c5-233">**WanLinkLogCollector.exe** это средство дает возможность его пользователя ввод необходимой информации.</span><span class="sxs-lookup"><span data-stu-id="225c5-233">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>
    
- <span data-ttu-id="225c5-234">**BandwidthUtilizationAnalyzer.xlsm** отчета программного обеспечения электронную таблицу Microsoft Excel автоматически запускается с WanLinkLogCollector.exe.</span><span class="sxs-lookup"><span data-stu-id="225c5-234">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="225c5-235">Это приложение позволяет пользователю применять фильтры к отчету, как описывается далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="225c5-235">This application allows the user to apply filters to the report as shown later in this article.</span></span>
    
#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="225c5-236">Этапы работы с анализатором использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="225c5-236">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="225c5-237">Работа с анализатором использования пропускной способности состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="225c5-237">There are two phases when using Bandwidth Utilization Analyzer:</span></span>
  
- <span data-ttu-id="225c5-238">сбор журналов, выполняемый с помощью программы WanLinkLogCollector.exe;</span><span class="sxs-lookup"><span data-stu-id="225c5-238">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>
    
- <span data-ttu-id="225c5-239">настройка отчетов, выполняемая с помощью электронной таблицы BandwidthUtilizationAnalyzer.xlsm.</span><span class="sxs-lookup"><span data-stu-id="225c5-239">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="225c5-240">Мы настоятельно рекомендуем конечным пользователям не запускать электронную таблицу BandwidthUtilizationAnalyzer.xlsm вручную.</span><span class="sxs-lookup"><span data-stu-id="225c5-240">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span> 
  
#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="225c5-241">Запуск анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="225c5-241">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="225c5-242">Запустите файл WanLinkLogCollector.exe с помощью командной строки или проводника.</span><span class="sxs-lookup"><span data-stu-id="225c5-242">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>
  
 <span data-ttu-id="225c5-243">**Использование программы WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="225c5-243">**Using WanLinkLogCollector.exe**</span></span>
  
<span data-ttu-id="225c5-244">Использование программы WanLinkLogCollector.exe включает три этапа.</span><span class="sxs-lookup"><span data-stu-id="225c5-244">There are three steps to using WanLinkLogCollector.exe:</span></span>
  
1. <span data-ttu-id="225c5-245">**Журнал временной шкалы** Предоставить временной шкалы, который требуется создать для отчета</span><span class="sxs-lookup"><span data-stu-id="225c5-245">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>
    
2. <span data-ttu-id="225c5-246">**Укажите каталогах файлов** Предоставляют сведения о размещении файлов</span><span class="sxs-lookup"><span data-stu-id="225c5-246">**Specify the file directories** Provide file location information</span></span>
    
3. <span data-ttu-id="225c5-247">**Сбор журналов и запустите средство просмотра отчетов** Выполните команду для создания отчета</span><span class="sxs-lookup"><span data-stu-id="225c5-247">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>
    
#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="225c5-248">Этап 1. Регистрация временной шкалы</span><span class="sxs-lookup"><span data-stu-id="225c5-248">Step 1 - Log the timeline</span></span>

<span data-ttu-id="225c5-249">Регистрация временной шкалы позволяет пользователю средства указать следующие сведения, как показано на рисунке ниже. </span><span class="sxs-lookup"><span data-stu-id="225c5-249">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span> 
  
1. <span data-ttu-id="225c5-250">**Дата начала** Это дата начала временной шкалы, отчет для; Например, 1 августа 2010 г.</span><span class="sxs-lookup"><span data-stu-id="225c5-250">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>
    
2. <span data-ttu-id="225c5-251">**Дата окончания** Дата окончания временной шкалы, отчет для; Например, 30 сентября 2010 г.</span><span class="sxs-lookup"><span data-stu-id="225c5-251">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
     ![Начальная и конечная дата анализа использования пропускной способности](../media/Reskit_2012_Tools_Documentation_Image4.jpg)
  
#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="225c5-253">Этап 2. Указание каталогов файлов</span><span class="sxs-lookup"><span data-stu-id="225c5-253">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="225c5-254">Пользователь может указать следующие каталоги файлов, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="225c5-254">The following file directories can be specified by the user as shown.</span></span>
  
- <span data-ttu-id="225c5-255">**Местоположение файлов журнала сервера** Местоположение папки, в котором хранятся журналы сервера политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="225c5-255">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="225c5-256">Это обычно в \<файлового сервера\>\\< choice из FE\>\AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="225c5-256">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>
    
- <span data-ttu-id="225c5-257">**Место хранения временных файлов** Временный файл места хранения промежуточных файлов во время которого создается отчет.</span><span class="sxs-lookup"><span data-stu-id="225c5-257">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>
    
![Каталоги файлов при анализе использования пропускной способности](../media/Reskit_2012_Tools_Documentation_Image5.jpg)
  
> [!NOTE]
> <span data-ttu-id="225c5-259">Пользователю средства необходимо предоставить достаточные права на доступ к файлам журналов сервера и папке хранения временных файлов.</span><span class="sxs-lookup"><span data-stu-id="225c5-259">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span> 
  
#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="225c5-260">Этап 3. Сбор журналов и запуск средства просмотра отчетов</span><span class="sxs-lookup"><span data-stu-id="225c5-260">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="225c5-p120">Чтобы выполнить сбор журналов и запустить средство просмотра отчетов, нажмите кнопку **Execute** (Выполнить), как показано ниже. На этом этапе собираются необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="225c5-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>
  
![Сбор данных в средстве анализа использования пропускной способности](../media/Reskit_2012_Tools_Documentation_Image6.jpg)
  
<span data-ttu-id="225c5-264">Если проверка входных данных прошла успешно, выводится показанное ниже сообщение.</span><span class="sxs-lookup"><span data-stu-id="225c5-264">When the input validation is successful, the message shown below is displayed.</span></span>
  
![Уведомление о сборе данных журналов в Bandwidth Utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)
  
<span data-ttu-id="225c5-p121">Нажмите кнопку **ОК**. Автоматически откроется электронная таблица BandwidthUtilizationAnalyzer.xlsm. Следуйте инструкциям в окне сообщения. Подробные сведения см. в следующем разделе, **Использование таблицы BandwidthUtilizationAnalyzer.xlsm**.</span><span class="sxs-lookup"><span data-stu-id="225c5-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>
  
#### 

### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="225c5-270">Использование таблицы BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="225c5-270">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="225c5-271">Когда таблица BandwidthUtilizationAnalyzer.xlsm автоматически откроется, нажмите кнопку **Refresh** (Обновить), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-271">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)
  
2. <span data-ttu-id="225c5-p122">Когда откроется папка с файлами, выберите файл consolidated.csv в папке, указанной в окне сообщения, как показано ниже. Папка будет указана как **C:\Temp**.</span><span class="sxs-lookup"><span data-stu-id="225c5-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>
    
     ![Открытие папки в BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)
  
3. <span data-ttu-id="225c5-276">Нажмите кнопку **Import** (Импорт).</span><span class="sxs-lookup"><span data-stu-id="225c5-276">Click **Import**.</span></span>
    
4. <span data-ttu-id="225c5-p123">Графический отчет будет создан автоматически. Он станет доступен, когда исчезнет указатель выполнения операции в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="225c5-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
     ![Применение фильтров в представлении отчета.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="225c5-280">Применение фильтров к представлению отчета</span><span class="sxs-lookup"><span data-stu-id="225c5-280">Applying Filters to the Report View</span></span>

<span data-ttu-id="225c5-281">Далее описываются фильтры, которые можно применить к представлению отчета и которые показаны ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-281">The filters that can be applied to the report view as shown below are described as follows:</span></span>
  
![Применение фильтров в представлении отчета.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
1. <span data-ttu-id="225c5-283">**Name** (Имя). Фильтрация по каналам глобальной сети (фильтр находится в правой части графика). Префикс означает следующие типы каналов (см. вертикальное (синее) поле):</span><span class="sxs-lookup"><span data-stu-id="225c5-283">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
  - <span data-ttu-id="225c5-284">**S (Site)** — канал глобальной сети между сетевым сайтом и областью сети;</span><span class="sxs-lookup"><span data-stu-id="225c5-284">**S Site** The WAN link from a network site to a network region</span></span>
    
  - <span data-ttu-id="225c5-285">**IS (Inter-Site)** — канал глобальной сети между двумя сетевыми сайтами;</span><span class="sxs-lookup"><span data-stu-id="225c5-285">**IS Inter-Site** The WAN link between two network sites</span></span>
    
  - <span data-ttu-id="225c5-286">**R (Inter-Region)** — канал глобальной сети между двумя областями сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-286">**R Inter-Region** The WAN link between two network region</span></span>
    
2. <span data-ttu-id="225c5-287">**Exceeded limit** (Превышение предела). Фильтрация каналов глобальной сети, использование полосы пропускания которых превышает доступные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="225c5-287">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>
    
3. <span data-ttu-id="225c5-288">**Critical levels** (Критические уровни). Фильтрация каналов глобальной сети, использование полосы пропускания которых достигло 90 % или более от максимального значения.</span><span class="sxs-lookup"><span data-stu-id="225c5-288">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>
    
4. <span data-ttu-id="225c5-289">**Under-utilized** (Недостаточное использование). Фильтрация каналов глобальной сети, использование полосы пропускания которых составляет менее 25 % от максимального.</span><span class="sxs-lookup"><span data-stu-id="225c5-289">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>
    
5. <span data-ttu-id="225c5-290">**Link type** (Тип канала). Фильтрация по следующим типам каналов глобальной сети:</span><span class="sxs-lookup"><span data-stu-id="225c5-290">**Link type** Filter by the following WAN links types:</span></span>
    
  - <span data-ttu-id="225c5-291">**Network site** (Сетевой сайт);</span><span class="sxs-lookup"><span data-stu-id="225c5-291">**Network site** type</span></span>
    
  - <span data-ttu-id="225c5-292">**Inter-site** (Между сайтами);</span><span class="sxs-lookup"><span data-stu-id="225c5-292">**Inter-site** type</span></span>
    
  - <span data-ttu-id="225c5-293">**Inter-Region link**(Канал между областями).</span><span class="sxs-lookup"><span data-stu-id="225c5-293">**Inter-Region link** type</span></span>
    
6. <span data-ttu-id="225c5-294">**Region** (Область). Фильтрация по области сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-294">**Region** Filter by network region</span></span>
    
<span data-ttu-id="225c5-295">На следующих рисунках показаны ранее описанные фильтры.</span><span class="sxs-lookup"><span data-stu-id="225c5-295">The following figures show the previously described filters.</span></span>
  
<span data-ttu-id="225c5-p124">Примените фильтр **Name**. Выберите список каналов, которые нужно показать на графике.</span><span class="sxs-lookup"><span data-stu-id="225c5-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>
  
![Фильтрация по имени в BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)
  
<span data-ttu-id="225c5-p125">Примените фильтр **Exceeded limit**. Установите флажок **True**, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="225c5-p125">Filter by **Exceeded limit**. Select **True** to enforce the filter.</span></span>
  
![Фильтрация по превышению ограничения.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)
  
<span data-ttu-id="225c5-p126">Примените фильтр **Critical levels**. Установите флажок **True**, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="225c5-p126">Filter by **Critical levels**. Select **True** to enforce the filter.</span></span>
  
![Фильтрация по критическим уровням.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)
  
<span data-ttu-id="225c5-p127">Примените фильтр **Under utilized**. Установите флажок **True**, чтобы применить фильтр.</span><span class="sxs-lookup"><span data-stu-id="225c5-p127">Filter by **Under utilized**. Select **True** to enforce the filter.</span></span>
  
![Фильтрация по параметру "Используется недостаточно".](../media/Reskit_2012_Tools_Documentation_Image15.jpg)
  
<span data-ttu-id="225c5-p128">Примените фильтр **Link Type**. Выберите один или несколько типов каналов, которые нужно показать.</span><span class="sxs-lookup"><span data-stu-id="225c5-p128">Filter by **Link Type**. Select the type or types that need to be displayed.</span></span>
  
![Фильтрация по типу ссылки.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)
  
<span data-ttu-id="225c5-p129">Примените фильтр **Region**. Выберите список областей, каналы которых нужно показать.</span><span class="sxs-lookup"><span data-stu-id="225c5-p129">Filter by **Region**. Select a list of regions whose links need to be displayed.</span></span>
  
![Фильтрация по региону.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)
  
### <a name="requirements"></a><span data-ttu-id="225c5-314">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-314">Requirements</span></span>

- <span data-ttu-id="225c5-315">Платформа .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="225c5-315">The .NET Framework 3.5</span></span>
    
- <span data-ttu-id="225c5-316">Microsoft Excel 2010 или Excel 2007</span><span class="sxs-lookup"><span data-stu-id="225c5-316">Microsoft Excel 2010 or Excel 2007</span></span>
    
### <a name="summary"></a><span data-ttu-id="225c5-317">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-317">Summary</span></span>

<span data-ttu-id="225c5-p130">Анализатор использования полосы пропускания предназначен для графического представления данных об использовании полосы пропускания звуковых каналов для трафика объединенных коммуникаций в сети. Это средство также можно использовать для создания отчетов об использовании полосы пропускания видеоканалов в сети.</span><span class="sxs-lookup"><span data-stu-id="225c5-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>
  
## <a name="call-parkometer"></a><span data-ttu-id="225c5-320">Счетчик парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="225c5-320">Call Parkometer</span></span>
<span data-ttu-id="225c5-321"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-321"></span></span>

<span data-ttu-id="225c5-322">Счетчик парковки вызовов — это программа командной строки, облегчающая доступ к базе данных орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="225c5-322">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-323">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-323">Description</span></span>

<span data-ttu-id="225c5-324">Счетчик парковки вызовов — это средство для отслеживания вызовов, находящихся в состоянии парковки на данный момент.</span><span class="sxs-lookup"><span data-stu-id="225c5-324">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="225c5-325">Оно также собирает статистику по орбитам и использованию сервера парковки вызовов (CPS).</span><span class="sxs-lookup"><span data-stu-id="225c5-325">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="225c5-326">Это средство командной строки предоставляет чтение и доступ на запись к орбиты CPS базы данных SQL Server с компьютера, локальный или удаленный подключение.</span><span class="sxs-lookup"><span data-stu-id="225c5-326">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>
  
<span data-ttu-id="225c5-p132">Все параметры являются взаимоисключающими. Синтаксис командной строки имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="225c5-p132">All options are mutually exclusive. Command-line syntax is as follows:</span></span>
  
- <span data-ttu-id="225c5-329">параметр **-o** — список всех Орбита диапазоны, настроенных для этого пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-329">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>
    
- <span data-ttu-id="225c5-330">параметр **-n** — списки, используемые в настоящее время все орбиты в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="225c5-330">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="225c5-331">Сведения, отображаемые выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="225c5-331">The information displayed is as follows:</span></span>
    
  - <span data-ttu-id="225c5-332">универсальный код ресурса (URI) протокола SIP паркуемого и паркующего;</span><span class="sxs-lookup"><span data-stu-id="225c5-332">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
  - <span data-ttu-id="225c5-333">имя узла сервера парковки вызовов, на котором паркуется вызов;</span><span class="sxs-lookup"><span data-stu-id="225c5-333">Host name of the CPS where the call is parked.</span></span>
    
  - <span data-ttu-id="225c5-334">метка времени парковки вызова;</span><span class="sxs-lookup"><span data-stu-id="225c5-334">Time stamp of when the call was parked.</span></span>
    
- <span data-ttu-id="225c5-335">параметр **-f** — количество свободного орбиты в пуле.</span><span class="sxs-lookup"><span data-stu-id="225c5-335">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>
    
- <span data-ttu-id="225c5-336">**-r \<n\> ** параметр — список \<n\> последнего парковка вызовов.</span><span class="sxs-lookup"><span data-stu-id="225c5-336">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="225c5-337">Сведения, отображаемые выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="225c5-337">The information displayed is as follows:</span></span>
    
  - <span data-ttu-id="225c5-338">URI SIP паркуемого;</span><span class="sxs-lookup"><span data-stu-id="225c5-338">Parkee SIP URI.</span></span>
    
  - <span data-ttu-id="225c5-339">URI SIP паркующего;</span><span class="sxs-lookup"><span data-stu-id="225c5-339">Parker SIP URI.</span></span>
    
  - <span data-ttu-id="225c5-340">имя узла сервера, на котором был припаркован вызов;</span><span class="sxs-lookup"><span data-stu-id="225c5-340">Host name of the CPS where the call was parked.</span></span>
    
  - <span data-ttu-id="225c5-341">метка времени извлечения или пропуска вызова;</span><span class="sxs-lookup"><span data-stu-id="225c5-341">Time stamp of when the call was retrieved or dropped.</span></span>
    
- <span data-ttu-id="225c5-342">**-t\<n\> ** параметр - тестируется резервирование орбиты в базе данных для отображения случайности номера назначенных орбиты.</span><span class="sxs-lookup"><span data-stu-id="225c5-342">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>
    
### <a name="output"></a><span data-ttu-id="225c5-343">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-343">Output</span></span>

<span data-ttu-id="225c5-344">В зависимости от входных параметров, указанных в командной строке, счетчик парковки вызовов отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="225c5-344">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>
  
- <span data-ttu-id="225c5-345">все диапазоны орбиты, настроенные для этого пула;</span><span class="sxs-lookup"><span data-stu-id="225c5-345">All orbit ranges that are configured for this pool</span></span>
    
- <span data-ttu-id="225c5-346">вызовы, припаркованные в настоящее время;</span><span class="sxs-lookup"><span data-stu-id="225c5-346">Currently parked calls</span></span>
    
- <span data-ttu-id="225c5-347">число свободных (доступных) орбит;</span><span class="sxs-lookup"><span data-stu-id="225c5-347">Number of free (available) orbits</span></span>
    
- <span data-ttu-id="225c5-348">недавно припаркованные вызовы;</span><span class="sxs-lookup"><span data-stu-id="225c5-348">Recently parked calls</span></span>
    
- <span data-ttu-id="225c5-349">зарезервированные орбиты для проверки универсальных и случайных значений орбиты.</span><span class="sxs-lookup"><span data-stu-id="225c5-349">Reserved orbits for testing uniform and random orbit values</span></span>
    
### <a name="purpose"></a><span data-ttu-id="225c5-350">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-350">Purpose</span></span>

<span data-ttu-id="225c5-p135">Средство CPS предназначено для предоставления доступа к базе данных CPS из командной строки. Администратор может просматривать сведения об использовании CPS и определять число орбит, назначенных пулу.</span><span class="sxs-lookup"><span data-stu-id="225c5-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="225c5-353">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-353">Requirements</span></span>

<span data-ttu-id="225c5-354">Если это средство запускается на компьютере с сервером парковки вызовов, то дополнительные требования не предъявляются.</span><span class="sxs-lookup"><span data-stu-id="225c5-354">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="225c5-355">Если это средство выполняется на удаленном компьютере, базы данных SQL Server, используемый Скайп для Business Server 2015 должен быть настроен на разрешение удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="225c5-355">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="225c5-356">Вызов Parkometer должны быть настроены строки подключения базы данных SQL Server для подключения к SQL Server пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-356">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="225c5-357">Эта строка подключения базы данных SQL Server определен в файле конфигурации **parkometer.exe.config**. Он должен помещен в ту же папку, где находится parkometer.exe.</span><span class="sxs-lookup"><span data-stu-id="225c5-357">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="225c5-358">Следующий XML-файл является примером parkometer.exe.config. Имя пользователя (например, mydomain\Administrator), пароль (например, mypassword) и имя узла (например, myserver) используются параметры, которые необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="225c5-358">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>
  
```
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

### <a name="examples"></a><span data-ttu-id="225c5-359">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-359">Examples</span></span>

<span data-ttu-id="225c5-360">Развертывание диапазонов орбит: параметр -o список всех диапазонов орбит, которые настроены для этого пула, как показано</span><span class="sxs-lookup"><span data-stu-id="225c5-360">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>
  
![Диапазоны орбит в службе парковки вызовов Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)
  
<span data-ttu-id="225c5-362">В настоящее время парковка вызовов: параметр - n перечислены все орбиты в настоящее время используемых в этом пуле, как показано</span><span class="sxs-lookup"><span data-stu-id="225c5-362">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>
  
![Вызовы, в настоящий момент приостановленные в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)
  
<span data-ttu-id="225c5-364">Количество свободного орбиты: параметр -f список количество свободного орбиты в пуле, как показано</span><span class="sxs-lookup"><span data-stu-id="225c5-364">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>
  
![Освобожденные орбиты в службе парковки вызовов Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)
  
<span data-ttu-id="225c5-366">Недавно парковка вызовов: - r \<n\> списки параметров \<n\> последнего приостанавливать вызовы, как показано</span><span class="sxs-lookup"><span data-stu-id="225c5-366">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>
  
![Недавно приостановленные вызовы в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)
  
<span data-ttu-id="225c5-368">Тестирование орбиты резервирования: -t \<n\> параметр тестируется резервирование орбиты в базе данных, как показано</span><span class="sxs-lookup"><span data-stu-id="225c5-368">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>
  
![Тестовые резервирования орбит в Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)
  
### <a name="summary"></a><span data-ttu-id="225c5-370">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-370">Summary</span></span>

<span data-ttu-id="225c5-371">Счетчик парковки вызовов — это средство командной строки, предоставляющее подробные сведения о сервере парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="225c5-371">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>
  
## <a name="dbanalyze"></a><span data-ttu-id="225c5-372">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="225c5-372">DBAnalyze</span></span>
<span data-ttu-id="225c5-373"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-373"></span></span>

### <a name="description"></a><span data-ttu-id="225c5-374">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-374">Description</span></span>

<span data-ttu-id="225c5-375">DBAnalyze — это средство командной строки, которая позволяет администраторам выполнять анализ отчеты о Скайп для баз данных Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-375">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="225c5-376">Средство DBAnalyze имеет следующие режимы: диагностика, пользовательские данные, конференция, узлы MCU и фрагментация дисков.</span><span class="sxs-lookup"><span data-stu-id="225c5-376">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>
  
- <span data-ttu-id="225c5-377">**Режим диагностики** Создает отчет, содержащий сведения о таблицах (количество записей, фрагментации, размер данных и размер индекса), размеры файлов данных и журналов, время последнего резервного копирования, контактов рассылки между серверами, на которых выполняется Microsoft Office Communications Server Среднее число разрешения, контакты, контейнеров, подписок, публикации, конечные точки для пользователей, любой неправильно перехода пользователей, пользователей, которые не могут быть маршрутизированы, среднее число конференций организовал для пользователей, назначенных конференций active конференций и версию базы данных.</span><span class="sxs-lookup"><span data-stu-id="225c5-377">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="225c5-378">Запуск средства в режиме диагностики может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="225c5-378">Running diagnostic mode can affect server performance.</span></span> 
  
- <span data-ttu-id="225c5-379">**Режим данных пользователя** Отчеты контакт, контейнер, подписки, публикации, разрешений и группы контактов данных для указанного пользователя или для пользователей, имеющих этого пользователя в свой список контактов и разрешений.</span><span class="sxs-lookup"><span data-stu-id="225c5-379">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="225c5-380">Этот режим также предоставляет сводные данные по конференциям, которые организовал пользователь или на которые он приглашен.</span><span class="sxs-lookup"><span data-stu-id="225c5-380">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>
    
- <span data-ttu-id="225c5-381">**Режим конференции** Подробные данные отчетов для определенного конференции, включая все сведения о времени расписания для конференции, в списке приглашаемому пользователю, в список типов мультимедиа разрешенные для конференции active MCUs (многоточечных управления единицы), список активных участников и каждый сигналы состояние участника.</span><span class="sxs-lookup"><span data-stu-id="225c5-381">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>
    
- <span data-ttu-id="225c5-382">**Декодирования идентификатор собрания** Декодирует телефонной сети общего пользования (PSTN) собрания идентификатор, указанный в параметре **/pstnid** , но не подключаются к внутренние серверы для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="225c5-382">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>
    
- <span data-ttu-id="225c5-383">**Разрешить конференции** Декодирует идентификатор собрания PSTN, указанного в параметре **/pstnid** и отображает сведения о конференции, указанный в параметре с идентификатором.</span><span class="sxs-lookup"><span data-stu-id="225c5-383">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>
    
- <span data-ttu-id="225c5-384">**Режим MCUs** Отчеты идентификатор, тип носителя, URL-адрес, состояние пульса, конференции нагрузки и участников нагрузки для каждого MCU в пуле.</span><span class="sxs-lookup"><span data-stu-id="225c5-384">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>
    
- <span data-ttu-id="225c5-385">**Режим степени фрагментации дисков** Отображает состояние фрагментации всех дисках.</span><span class="sxs-lookup"><span data-stu-id="225c5-385">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>
    
<span data-ttu-id="225c5-p139">Администраторы могут использовать это средство для диагностики различных проблем или при планировании емкости. Например, если большинство пользователей, размещенных на сервере А, выбрали в качестве контактов пользователей, размещенных на сервере Б, администратор может перенести пользователей с сервера А на сервер Б, чтобы уменьшить объем трафика между серверами.</span><span class="sxs-lookup"><span data-stu-id="225c5-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>
  
### <a name="output"></a><span data-ttu-id="225c5-388">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-388">Output</span></span>

<span data-ttu-id="225c5-389">Это средство выводит предварительно определенные отчеты о Скайп для базы данных Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-389">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="225c5-390">**Путь**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="225c5-390">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>
  
### <a name="purpose"></a><span data-ttu-id="225c5-391">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-391">Purpose</span></span>

<span data-ttu-id="225c5-392">Чтобы установить Dbanalyze.exe, скопируйте его в локальную папку и запустите средство.</span><span class="sxs-lookup"><span data-stu-id="225c5-392">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="225c5-393">Чтобы использовать средство, выполните следующую команду из командной строки.</span><span class="sxs-lookup"><span data-stu-id="225c5-393">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="225c5-394">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Ниже перечислены описания параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="225c5-394">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>
  
![Параметры командной строки для Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)
  
### <a name="requirements"></a><span data-ttu-id="225c5-396">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-396">Requirements</span></span>

 <span data-ttu-id="225c5-397">**Компьютер** DBAnalyze может выполняться только с компьютера, присоединенный к домену, который имеет Скайп для Business Server 2015 установлены.</span><span class="sxs-lookup"><span data-stu-id="225c5-397">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>
  
 <span data-ttu-id="225c5-398">**Сеть**. Компьютер должен иметь возможность подключения к внутренней базе данных.</span><span class="sxs-lookup"><span data-stu-id="225c5-398">**Network** The computer should be able to connect to the back-end database.</span></span>
  
 <span data-ttu-id="225c5-399">**Программное обеспечение** Перед запуском DBAnalyze необходимо установить Скайп для компонентов программного обеспечения Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-399">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>
  
 <span data-ttu-id="225c5-400">**Пользователи** В следующей таблице перечислены администраторов пользователей, которые имеют необходимые разрешения для доступа к Скайп для баз данных Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-400">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>
  
![Таблица разрешений для Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)
  
> [!NOTE]
> <span data-ttu-id="225c5-402">Для режима **/report:disk** необходима учетная запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="225c5-402">A local administrator account is required for **/report:disk** mode.</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-403">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-403">Examples</span></span>

<span data-ttu-id="225c5-404">Ниже приведены примеры допустимых команд Dbanalyze.exe.</span><span class="sxs-lookup"><span data-stu-id="225c5-404">The following are examples of valid Dbanalyze.exe commands:</span></span>
  
```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="225c5-405">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-405">Summary</span></span>

<span data-ttu-id="225c5-406">DBAnalyzer предоставляет администраторам быстро и легко анализировать Скайп для баз данных Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-406">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>
  
## <a name="import-storage-service-data"></a><span data-ttu-id="225c5-407">Импорт данных службы хранилища</span><span class="sxs-lookup"><span data-stu-id="225c5-407">Import Storage Service Data</span></span>
<span data-ttu-id="225c5-408"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-408"></span></span>

<span data-ttu-id="225c5-409">Средство ImportStorageServiceData из набора ресурсов позволяет повторно импортировать данные очереди и конечных точек, записанные на диск из службы хранилища (LYSS), обратно в эту службу.</span><span class="sxs-lookup"><span data-stu-id="225c5-409">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-410">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-410">Description</span></span>

<span data-ttu-id="225c5-411">Данные могут записываться на диск из службы хранилища автоматически (периодически) в зависимости от состояния элемента очереди или размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="225c5-411">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="225c5-412">Это может происходить в результате вызова командлета отработки отказа пула вручную или вызова командлета StorageServiceFullFlush (командлетом отработки отказа пула).</span><span class="sxs-lookup"><span data-stu-id="225c5-412">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="225c5-413">Обратите внимание, что в идеальном варианте не следует повторно импортировать данные в случае любого размера базы данных службы хранения (LYSS) на интерфейсных выше обычного уровня, так как это может просто привести к дополнительные данные для экспорта обратно в работе. Кроме того проблем, которые может повлиять на ошибки, возникающие очереди службы хранения на случай увеличения сначала должно быть разрешено (для пример Exchange конечной точки ошибки, неполадки с сетью или другие неполадки с).</span><span class="sxs-lookup"><span data-stu-id="225c5-413">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>
  
 <span data-ttu-id="225c5-414">**Сценарий 1:** во время отработки отказа, файлы могут сброшены из службы хранилища для каждого сервера переднего плана в работе.</span><span class="sxs-lookup"><span data-stu-id="225c5-414">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="225c5-415">После завершения перехода на другой ресурс следует запускать средство повторно импортируйте данные.</span><span class="sxs-lookup"><span data-stu-id="225c5-415">After failover is completed, the tool should be run to re-import the data.</span></span>
  
 <span data-ttu-id="225c5-416">**Сценарий 2**.</span><span class="sxs-lookup"><span data-stu-id="225c5-416">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="225c5-417">Данные записываются на диск автоматически каждый день или при превышении базой данных службы хранилища определенного порогового значения размера (например заполненность на 60, 80 или 90 %).</span><span class="sxs-lookup"><span data-stu-id="225c5-417">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="225c5-418">В приведенном выше ситуации Если пакет мониторинга SCOM не развернуто, существует события для Скайп для службы хранилища сервера Business, относящиеся к данным, записи на диск в службе хранилища.</span><span class="sxs-lookup"><span data-stu-id="225c5-418">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="225c5-419">Идентификаторы событий из 32075 (полное сброса операция запускается), 32076 (завершения полной очистки), 32082 (обслуживания уровень сброса работы), 32083 (flush полный уровень обслуживания), 32089 (Очистка произошла из-за заполнения базы данных).</span><span class="sxs-lookup"><span data-stu-id="225c5-419">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="225c5-420">Обратите внимание, что эти идентификаторы событий соответствуют окончательному первоначальному выпуску (RTM).</span><span class="sxs-lookup"><span data-stu-id="225c5-420">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="225c5-421">Когда администратор видит эти события, оно означает, что файлы, которые были сброшены в работе. В этом следует регулярно импортировать данные обратно с помощью этого средства, например один раз в неделю.</span><span class="sxs-lookup"><span data-stu-id="225c5-421">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>
  
<span data-ttu-id="225c5-422">Обновление веб-службами Если развернут пакет SCOM для Скайп Business Server для наблюдения за работоспособностью системы, существует оповещения о новых которых могут быть созданы, которые обратитесь к администратору, чтобы повторно импортируйте данные сброшены обратно в хранилище службы.</span><span class="sxs-lookup"><span data-stu-id="225c5-422">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="225c5-423">Будет соответствующего события в журнале событий на сервере переднего плана, который запускается оповещение.</span><span class="sxs-lookup"><span data-stu-id="225c5-423">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="225c5-424">Событие дает описание родительского пути, в котором находятся файлы данные сброшены, а также как существует много файлов являются которого условиям оповещения.</span><span class="sxs-lookup"><span data-stu-id="225c5-424">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="225c5-425">Условий оповещения является наличие расположены X или несколько файлов в разделе конкретный родительский путь, который находится на наименее Y дней (где X и Y заданы в StorageService, но можно переопределить с помощью изменения файла APPCONFIG.) Ниже, показаны два примера события, которые может активировать оповещение о работоспособности с разницы выполняется их родительского пути.</span><span class="sxs-lookup"><span data-stu-id="225c5-425">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="225c5-426">Один из вариантов является в разделе веб-службы общих папках, а другие возможности — это локальный каталог Application Data каждого переднего плана.</span><span class="sxs-lookup"><span data-stu-id="225c5-426">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="225c5-427">(например c:\ProgramData\Microsoft\Skype для 2015\StorageService Business Server).</span><span class="sxs-lookup"><span data-stu-id="225c5-427">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="225c5-428">Администратор будет запускаться этого средства пакета ресурсов.</span><span class="sxs-lookup"><span data-stu-id="225c5-428">The administrator will then run this reskit tool.</span></span>
  
<span data-ttu-id="225c5-429">Это средство повышает загрузку ЦП и интенсивность операций ввода-вывода на сервере переднего плана, на котором оно запущено, а также на других серверах переднего плана, если данные не принадлежат серверу, на котором выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="225c5-429">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="225c5-430">Мы не рекомендуем запускать это средство, когда загрузка ЦП и интенсивность операций ввода-вывода на серверах переднего плана высоки (например, в часы пиковой нагрузки).</span><span class="sxs-lookup"><span data-stu-id="225c5-430">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="225c5-431">Во-вторых, на импорт одного файла данных средству может потребоваться 2–3 минуты.</span><span class="sxs-lookup"><span data-stu-id="225c5-431">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="225c5-432">Учитывайте это при оценке времени работы средства.</span><span class="sxs-lookup"><span data-stu-id="225c5-432">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="225c5-433">Подробный файл журнала, создаваемый средством, по умолчанию находится в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="225c5-433">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="225c5-434">Удалите его, если он не содержит ошибок, так как его размер может составлять десятки мегабайт и более.</span><span class="sxs-lookup"><span data-stu-id="225c5-434">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>
  
![События журнала событий сервера Sample Storage Server.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)
  
### <a name="requirements"></a><span data-ttu-id="225c5-436">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-436">Requirements</span></span>

<span data-ttu-id="225c5-437">Установка Скайп для Business Server 2015 Resource Kit tools.</span><span class="sxs-lookup"><span data-stu-id="225c5-437">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="225c5-438">Будет запущена на присоединенный к домену машины установленными Скайп для Business Server и Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-438">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="225c5-439">Средство использует командлет из командной консоли для идентификации всех серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="225c5-439">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="225c5-440">Во-вторых средство должна быть выполнена с компьютера в пул, в котором установлен базу данных **RtcLocal** .</span><span class="sxs-lookup"><span data-stu-id="225c5-440">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="225c5-441">Эта база данных используется с помощью данного средства для извлечения расположение WEBSERVICE общий файловый ресурс для пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-441">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="225c5-442">Кроме того перед использованием этого инструмента, каждый сервер переднего плана сначала необходимо включить удаленного взаимодействия Windows PowerShell, с помощью **Enable-PSRemoting** на каждом сервере переднего плана, а также компьютера, на котором выполняется средство.</span><span class="sxs-lookup"><span data-stu-id="225c5-442">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="225c5-443">В противном случае удаленных команд Windows PowerShell из этой программы завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="225c5-443">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="225c5-444">Об удаленном взаимодействии Windows PowerShell может быть отключена на всех серверах переднего плана в пуле после его завершения.</span><span class="sxs-lookup"><span data-stu-id="225c5-444">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="225c5-445">Наконец учетной записи или учетных данных, вызов средства должны иметь разрешение на чтение и запись в общую папку файлов webservice для пула, в котором они выполняются это средство на.</span><span class="sxs-lookup"><span data-stu-id="225c5-445">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="225c5-446">В противном случае — средство завершится ошибкой при этом возникают ошибки ввода-ВЫВОДА разрешений.</span><span class="sxs-lookup"><span data-stu-id="225c5-446">Otherwise the tool will fail with IO Permission errors.</span></span>
  
> [!NOTE]
> <span data-ttu-id="225c5-447">В Windows Server 2012 об удаленном взаимодействии Windows PowerShell включена по умолчанию, но не в операционной системе Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="225c5-447">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span> 
  
### <a name="examples"></a><span data-ttu-id="225c5-448">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-448">Examples</span></span>

```
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

## <a name="lcssync"></a><span data-ttu-id="225c5-449">LCSSync</span><span class="sxs-lookup"><span data-stu-id="225c5-449">LCSSync</span></span>
<span data-ttu-id="225c5-450"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-450"></span></span>

<span data-ttu-id="225c5-451">Средство LCSSync помогает развертывания Скайп для программного обеспечения Business Server 2015 в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="225c5-451">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="225c5-452">Это средство используется для синхронизации пользователей и групп из лесов другого пользователя в доменных службах Active Directory обратитесь объект, который требуется центральный лес, установленными Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-452">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-453">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-453">Description</span></span>

 <span data-ttu-id="225c5-454">Использование LCSSync синхронизированного доменных служб Active Directory контактов объектов в центральном лесу Включение пользователей для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-454">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="225c5-455">Для обеспечения единого входа в систему, учетная запись основной должен быть сопоставлен объекта контакта доменных служб Active Directory в центральном лесу для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-455">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="225c5-456">Это средство помогает выполнить такое сопоставление.</span><span class="sxs-lookup"><span data-stu-id="225c5-456">This tool helps perform that mapping.</span></span> <span data-ttu-id="225c5-457">Оно предоставляет шаблоны для создания агентов управления на сервере Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-457">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>
  
### <a name="summary"></a><span data-ttu-id="225c5-458">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-458">Summary</span></span>

<span data-ttu-id="225c5-459">Средство LCSSync помогает развертывания Скайп для Business Server 2015 в среде с несколькими лесами.</span><span class="sxs-lookup"><span data-stu-id="225c5-459">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>
  
## <a name="lookup-user-console"></a><span data-ttu-id="225c5-460">Консоль поиска пользователей</span><span class="sxs-lookup"><span data-stu-id="225c5-460">Lookup User Console</span></span>
<span data-ttu-id="225c5-461"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-461"></span></span>

<span data-ttu-id="225c5-462">Средство LookupUserConsole отображает внутреннего Скайп Business Server маршрутизации сведения о конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="225c5-462">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="225c5-463">Эти сведения могут быть полезны специалистам службы поддержки Майкрософт при диагностике проблем с развертыванием и маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="225c5-463">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-464">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-464">Description</span></span>

 <span data-ttu-id="225c5-465">Выполнение LookupUserConsole.exe будет откройте командную строку, которая принимает SIP-адреса и пытается отобразить внутреннего Скайп Business Server маршрутизации сведения, связанные с ними.</span><span class="sxs-lookup"><span data-stu-id="225c5-465">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="225c5-466">Чтобы выйти из средства LookupUserConsole, введите команду **exit**.</span><span class="sxs-lookup"><span data-stu-id="225c5-466">Type **exit** to quit the LookupUserConsole tool.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="225c5-467">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-467">Requirements</span></span>

<span data-ttu-id="225c5-468">Установка Скайп for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="225c5-468">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="225c5-469">Будет запущена на присоединенный к домену машины установленными Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-469">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-470">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-470">Examples</span></span>

<span data-ttu-id="225c5-471">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="225c5-471">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>
  
```
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

## <a name="msturnping"></a><span data-ttu-id="225c5-472">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="225c5-472">MsTurnPing</span></span>
<span data-ttu-id="225c5-473"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-473"></span></span>

<span data-ttu-id="225c5-474">Средство MSTurnPing позволяет администратору Скайп для программного обеспечения Business Server 2015 для проверки состояния серверов под управлением службы пограничного сервера аудио/видео и проверки подлинности аудио и видео, а также серверы, на которых выполняется политика пропускной способности Службы в топологии.</span><span class="sxs-lookup"><span data-stu-id="225c5-474">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-475">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-475">Description</span></span>

<span data-ttu-id="225c5-476">Средство MSTurnPing позволяет администратору Скайп для программного обеспечения Business Server 2015 для проверки состояния серверов под управлением службы пограничного сервера аудио/видео и проверки подлинности аудио и видео, а также серверы, на которых выполняется политика пропускной способности Службы в топологии.</span><span class="sxs-lookup"><span data-stu-id="225c5-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>
  
<span data-ttu-id="225c5-477">Средство позволяет администратору выполнять перечисленные ниже проверки.</span><span class="sxs-lookup"><span data-stu-id="225c5-477">The tool allows the administrator to perform the following tests:</span></span>
  
1. <span data-ttu-id="225c5-478">Проверка пограничных серверов аудио- и видеоданных — средство тестирует все пограничные серверы аудио- и видеоданных в топологии, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="225c5-478">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
  - <span data-ttu-id="225c5-479">Проверка, что Скайп для службы проверки подлинности аудио/видео Business Server запущена и может выдавать правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="225c5-479">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
  - <span data-ttu-id="225c5-480">Проверка, что Скайп для службы пограничного сервера аудио/видео Business Server запущена и можно распределить ресурсы на внешний пограничный сервер успешно.</span><span class="sxs-lookup"><span data-stu-id="225c5-480">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>
    
2. <span data-ttu-id="225c5-481">Проверка службы политики пропускной способности — средство тестирует все серверы в топологии, на которых запущены службы политики пропускной способности, выполняя следующие действия:</span><span class="sxs-lookup"><span data-stu-id="225c5-481">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
  - <span data-ttu-id="225c5-482">Проверка, что Скайп для службы политики пропускной способности Business Server (проверка подлинности) запущена и может выдавать правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="225c5-482">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
  - <span data-ttu-id="225c5-483">Проверка, что Скайп для службы политики пропускной способности Business Server (ядро) запущена и можно успешно выполнить проверку пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="225c5-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>
    
<span data-ttu-id="225c5-484">Это средство необходимо запускать на компьютере, который входит в топологию и на котором установлено локальное хранилище. </span><span class="sxs-lookup"><span data-stu-id="225c5-484">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span> 
  
### <a name="output"></a><span data-ttu-id="225c5-485">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-485">Output</span></span>

<span data-ttu-id="225c5-486">Средство выводит результаты каждой операции.</span><span class="sxs-lookup"><span data-stu-id="225c5-486">The tool outputs the results of each of the operations.</span></span>
  
- <span data-ttu-id="225c5-487">Если выполняется тест **AudioVideoEdgeServer**, выходные данные включают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="225c5-487">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
  - <span data-ttu-id="225c5-488">Результаты теста компьютеры, которые предоставляют Скайп для службы проверки подлинности Business Server 2015 аудио и видео в топологии</span><span class="sxs-lookup"><span data-stu-id="225c5-488">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>
    
  - <span data-ttu-id="225c5-489">Результаты теста компьютеры, которые предоставляют Скайп для службы пограничного сервера Business Server 2015 аудио и видео в топологии</span><span class="sxs-lookup"><span data-stu-id="225c5-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>
    
- <span data-ttu-id="225c5-490">Если выполняется тест **BandwidthPolicyServer**, выходные данные включают следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="225c5-490">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
  - <span data-ttu-id="225c5-491">Результаты теста компьютеры, которые обеспечивают Скайп для службы политики пропускной способности Server 2015 Business (проверка подлинности) в топологии</span><span class="sxs-lookup"><span data-stu-id="225c5-491">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>
    
  - <span data-ttu-id="225c5-492">Результаты теста компьютеры, которые обеспечивают Скайп для службы политики пропускной способности Server 2015 Business (ядро) в топологии</span><span class="sxs-lookup"><span data-stu-id="225c5-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>
    
### <a name="requirements"></a><span data-ttu-id="225c5-493">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-493">Requirements</span></span>

- <span data-ttu-id="225c5-494">Это средство необходимо запускать на компьютере, который входит в топологию и на котором установлено локальное хранилище.</span><span class="sxs-lookup"><span data-stu-id="225c5-494">This tool must be run from a computer that is in the topology and that has the local store.</span></span>
    
- <span data-ttu-id="225c5-495">Средство должно запускаться администратором, который имеет доступ к локальному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="225c5-495">The tool must be run as an administrator who has access to the local store.</span></span>
    
### <a name="examples"></a><span data-ttu-id="225c5-496">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-496">Examples</span></span>

<span data-ttu-id="225c5-497">Ниже приведен пример входных данных средства.</span><span class="sxs-lookup"><span data-stu-id="225c5-497">The following is an example of the tool input.</span></span>
  
```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="225c5-498">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-498">Summary</span></span>

<span data-ttu-id="225c5-499">Это средство может быть ценных ресурсов для Скайп для администраторов Business Server 2015, чтобы проверить состояние серверов, использующих аудио и видео и службы политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="225c5-499">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>
  
## <a name="network-configuration-viewer"></a><span data-ttu-id="225c5-500">Средство просмотра конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="225c5-500">Network Configuration Viewer</span></span>
<span data-ttu-id="225c5-501"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-501"></span></span>

<span data-ttu-id="225c5-502">Можно использовать средство просмотра конфигурации сети с Скайп для администраторов программного обеспечения Business Server 2015 communications Просмотр топологии сети контроля допуска звонков допуска предприятия, которая может разрешать сеансы связи в режиме реального времени, таких как голосовые звонки и видеозвонки на основе указанного емкости пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="225c5-502">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="225c5-503">Скайп Business Server 2015 администраторам определить политики контроля допуска звонков, которые применяются службы политики пропускной способности, которые устанавливаются вместе с Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-503">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-504">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-504">Description</span></span>

<span data-ttu-id="225c5-505">Средство просмотра конфигурации сети (NetworkConfigurationViewer.exe) позволяет администраторам выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="225c5-505">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>
  
- <span data-ttu-id="225c5-506">Загрузите и Просмотр топологии сети CAC из Скайп для развертывания Business Server 2015 в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="225c5-506">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>
    
- <span data-ttu-id="225c5-507">загружать и просматривать сетевую топологию CAC из файла журнала сервера политики пропускной способности в графическом формате;</span><span class="sxs-lookup"><span data-stu-id="225c5-507">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>
    
- <span data-ttu-id="225c5-508">сохранять сетевую топологию CAC в формате XML на диске;</span><span class="sxs-lookup"><span data-stu-id="225c5-508">Save and store CAC network topology in an XML format on the disk.</span></span>
    
- <span data-ttu-id="225c5-509">сохранять схему сетевой топологии CAC в формате JPG или BMP;</span><span class="sxs-lookup"><span data-stu-id="225c5-509">Save and store CAC network topology diagram in JPG or BMP format.</span></span>
    
- <span data-ttu-id="225c5-510">просматривать данные конфигурации сетевой топологии CAC;</span><span class="sxs-lookup"><span data-stu-id="225c5-510">View CAC network topology configuration data.</span></span>
    
- <span data-ttu-id="225c5-511">просматривать сетевую топологию CAC в виде древовидного представления;</span><span class="sxs-lookup"><span data-stu-id="225c5-511">View CAC network topology in a tree-view style.</span></span>
    
- <span data-ttu-id="225c5-512">определять настраиваемые соединители для каналов сетевой топологии CAC (например каналов между сайтом и областью, между двумя областями или между двумя сайтами);</span><span class="sxs-lookup"><span data-stu-id="225c5-512">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>
    
- <span data-ttu-id="225c5-513">просматривать сведения о сайтах и областях сетевой топологии CAC, а также о настроенных политиках пропускной способности и сетевых каналах.</span><span class="sxs-lookup"><span data-stu-id="225c5-513">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>
    
### <a name="purpose"></a><span data-ttu-id="225c5-514">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-514">Purpose</span></span>

<span data-ttu-id="225c5-515">Просмотр каналов корпоративной сетевой топологии CAC в графическом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="225c5-515">View enterprise CAC network topology links in a graphical interface.</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-516">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-516">Examples</span></span>

 <span data-ttu-id="225c5-517">**Загрузка и Просмотр топологии сети CAC из Скайп для развертывания Business Server 2015 в виде графического**: Скайп для администраторов Business Server 2015 можно загружать и просматривать конфигурации топологии сети CAC на любой Скайп для компьютера Business Server 2015, с помощью параметра **Загрузки конфигурации сети** , как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="225c5-517">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="225c5-518">Средство не удастся загрузить или просмотра такой конфигурации при развертывании на компьютере, который не имеет возможность подключения к Скайп для хранилища конфигурации Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-518">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>
  
![Загрузка конфигурации сети.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)
  
 <span data-ttu-id="225c5-520">**Нагрузки и просмотр CAC топологии сети из файла журнала сервера политики пропускной способности в графическом формате:** Скайп для серверов Business Server 2015 полосы пропускания сохраните топологии сети CAC как часть механизм ведения журнала в разделе Скайп Business Server 2015 расположение общей папки.</span><span class="sxs-lookup"><span data-stu-id="225c5-520">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="225c5-521">Скайп для администраторов Business Server 2015 можно просмотреть этот файл в графическом формате с помощью параметра **Open конфигурации сети** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-521">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>
  
![Открытие файла журнала сервера Bandwidth Policy Server.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)
  
<span data-ttu-id="225c5-523">Сохранить и сохраните топологию сети CAC в формате XML на диске: Скайп для администраторов Business Server 2015 можно сохранить файл конфигурации топологии сети CAC в формате XML, выбрав пункт **Сохранить копию конфигурации сети** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-523">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="225c5-524">Сохраненный файл конфигурации может использоваться для целей графический просмотра нажмите автономный режим.</span><span class="sxs-lookup"><span data-stu-id="225c5-524">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>
  
![Сохранение конфигурации сети как XML-файл.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)
  
<span data-ttu-id="225c5-526">Схема топологии сети CAC хранилища в формате JPG или BMP и сохранить: Скайп для администраторов Business Server 2015 можно сохранить конфигурации топологии сети CAC в графическом формате (форматы файлов JPG и BMP) с помощью схемы **Сохранить настройки сети в виде Рисунок** как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-526">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>
  
![Сохранение конфигурации сети как изображение.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)
  
 <span data-ttu-id="225c5-528">**Данные конфигурации топологии сети CAC представления:** Скайп для администраторов Business Server 2015 можно просмотреть данные конфигурации сети, связанных с ними рабочих областей сети, сети, профили пропускной способности и сайта подсети IP-адресов в текстовый формат с помощью параметра данные конфигурации сети представления, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-528">**View CAC network topology configuration data:**Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span> 
  
![Просмотр данных конфигурации сети.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)
  
 <span data-ttu-id="225c5-530">**Топология сети CAC представления в древовидном представлении стилей:** Скайп Business Server 2015 администраторы могут просматривать данные о конфигурации сети, связанных с ними в стиль представления графического дерева с помощью панели управления в левой части окна инструментов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-530">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>
  
![Просмотр данных конфигурации сети в представлении дерева.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)
  
 <span data-ttu-id="225c5-532">**Определение настраиваемых соединителей для контроля допуска звонков связи топологии (например, расположение узла, -регионах и веб сайта ссылки):** Скайп для администраторов Business Server 2015 можно определить настраиваемых графический соединителей для контроля допуска звонков сетевой конфигурации каналов связи ГЛОБАЛЬНОЙ сети с помощью параметра параметров, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="225c5-532">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="225c5-533">Это помогает различать различные типы сетевых соединений, подготавливаются для сетевой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="225c5-533">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>
  
![Инструменты](../media/Reskit_2012_Tools_Documentation_Image29.jpg)
  
 <span data-ttu-id="225c5-535">**Сведения о сайте топологии сети CAC представления, сведений об области и политики пропускной способности подготовленных:** Скайп для администраторов Business Server 2015 можно просмотреть, связанных с ними сведений о сетевом регионе CAC, сведения о сайте и полосы пропускания CAC подготовки, используя параметры, приведенные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="225c5-535">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="225c5-536">(Например, нажмите кнопку **сведения** в области сети или сетевого узла объекта.)</span><span class="sxs-lookup"><span data-stu-id="225c5-536">(For example, click **Info** in a network region or network site object.)</span></span>
  
![Определение настраиваемого соединителя для сети.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)
  
### <a name="summary"></a><span data-ttu-id="225c5-538">Заключение</span><span class="sxs-lookup"><span data-stu-id="225c5-538">Summary</span></span>

<span data-ttu-id="225c5-539">Это средство может быть ценных ресурсов для Скайп для администраторов Business Server 2015, которые хотите просмотреть топологии сети CAC для их развертывания в графическом формате.</span><span class="sxs-lookup"><span data-stu-id="225c5-539">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>
  
## <a name="response-group-agent-live"></a><span data-ttu-id="225c5-540">Динамический агент группы ответа</span><span class="sxs-lookup"><span data-stu-id="225c5-540">Response Group Agent Live</span></span>
<span data-ttu-id="225c5-541"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-541"></span></span>

<span data-ttu-id="225c5-542">Приложение группы ответа позволяет агентам для доступа к полезную информацию в реальном времени, с помощью его встроенной веб-службы.</span><span class="sxs-lookup"><span data-stu-id="225c5-542">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="225c5-543">К сожалению нет графического представления эти данные недоступны вне приложения.</span><span class="sxs-lookup"><span data-stu-id="225c5-543">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="225c5-544">Средство ответа группы агентов Live Resource Kit решает эту проблему, предоставляя простой и графический способ доступа к эти сведения, улучшена благодаря Скайп в режиме реального времени для бизнес-коммуникаций программного обеспечения информация таких как сведения о присутствии других агентов.</span><span class="sxs-lookup"><span data-stu-id="225c5-544">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-545">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-545">Description</span></span>

<span data-ttu-id="225c5-546">Динамический агент группы ответа — это приложение Windows, которое предоставляет агентам группы ответа функции входа и выхода и некоторые сведения в режиме реального времени (такие как членство в группах и текущее число звонков).</span><span class="sxs-lookup"><span data-stu-id="225c5-546">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="225c5-547">Он должен быть улучшенной версии страницу группы агентов (доступен из Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="225c5-547">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="225c5-548">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-548">Purpose</span></span>

<span data-ttu-id="225c5-p161">Приложение группы ответа помещает входящие звонки в очередь, а затем направляет их группам агентов. Для принятия обоснованных решений по поводу того, какие звонки следует обслуживать, агенты могут получать доступ к информации о своих группах агентов в режиме реального времени, например к сведениям о том, какие еще агенты доступны и сколько звонков помещено в каждую очередь. Динамический агент группы ответа обеспечивает интуитивно понятный доступ к этой информации, которая ранее была доступна только через службу группы ответа.</span><span class="sxs-lookup"><span data-stu-id="225c5-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>
  
#### <a name="features"></a><span data-ttu-id="225c5-552">Возможности</span><span class="sxs-lookup"><span data-stu-id="225c5-552">Features</span></span>

<span data-ttu-id="225c5-553">Средство Live агента группы ответа — это от службы группы ответа и Скайп построенными на базе Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="225c5-553">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="225c5-554">Он предоставляет агентам группы ответа информацию и возможности, доступные в службе группе ответа (например сведения о членстве в группах, присутствии других агентов и числе ожидающих звонков).</span><span class="sxs-lookup"><span data-stu-id="225c5-554">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>
  
<span data-ttu-id="225c5-555">На рисунке ниже показан главный интерфейс динамического агента группы ответа.</span><span class="sxs-lookup"><span data-stu-id="225c5-555">The figure below illustrates the main interface of Response Group Agent Live.</span></span>
  
![Инструмент Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)
  
<span data-ttu-id="225c5-557">В динамическом агенте группы ответа доступны следующие три основные функции.</span><span class="sxs-lookup"><span data-stu-id="225c5-557">The following three main features are available for agents in Response Group Agent Live:</span></span>
  
- <span data-ttu-id="225c5-558">**Sign-in/out:** В отличие от (доступен Скайп для Business Server 2015) страницу группы агентов Live агента группы ответа позволяет только агентам для входа в систему или из него все агента группам за один раз.</span><span class="sxs-lookup"><span data-stu-id="225c5-558">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="225c5-559">Это приложение предоставляет агентам три быстрых способа входа или выхода.</span><span class="sxs-lookup"><span data-stu-id="225c5-559">This application provides three quick ways for agents to sign in or out:</span></span>
    
  - <span data-ttu-id="225c5-560">Нажмите в приложении кнопку входа или выхода (зеленую или красную соответственно).</span><span class="sxs-lookup"><span data-stu-id="225c5-560">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
  - <span data-ttu-id="225c5-561">Щелкните значок в области уведомлений и выберите команду входа или выхода.</span><span class="sxs-lookup"><span data-stu-id="225c5-561">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
  - <span data-ttu-id="225c5-562">Используйте настраиваемые сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="225c5-562">Using configurable keyboard shortcuts.</span></span>
    
- <span data-ttu-id="225c5-563">**Членства:** При выборе группы агента Live агента группы ответа отображается список агентов в эту группу в правой области.</span><span class="sxs-lookup"><span data-stu-id="225c5-563">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="225c5-564">Если Скайп для Business Server 2015 работает на том же компьютере, что это приложение, сведения о присутствии и карточке контакта отображаются в Live агента группы ответа.</span><span class="sxs-lookup"><span data-stu-id="225c5-564">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="225c5-565">Агенты могут отправлять мгновенные сообщения или звонить другим агентам непосредственно отсюда.</span><span class="sxs-lookup"><span data-stu-id="225c5-565">Agents can send an IM or call other agents directly from there.</span></span>
    
- <span data-ttu-id="225c5-p165">**Статистика в режиме реального времени**. Динамический агент группы ответа предоставляет статистику в режиме реального времени по всем группам агентов. Частота обновления составляет одну минуту. Когда группа ответа отвечает на звонок, рядом с именем группы появляется визуальный индикатор с текущим числом звонков в очереди. Если навести указатель на группу, также отображается самое долгое время ожидания.</span><span class="sxs-lookup"><span data-stu-id="225c5-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="225c5-570">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-570">Requirements</span></span>

<span data-ttu-id="225c5-571">Для динамического агента группы ответа требуется платформа .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="225c5-571">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="225c5-572">Кроме того чтобы воспользоваться преимуществами функций карточки контакта и сведения о присутствии, Скайп для бизнеса должно быть установлено локально (и работать под управлением).</span><span class="sxs-lookup"><span data-stu-id="225c5-572">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>
  
#### <a name="configuration"></a><span data-ttu-id="225c5-573">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="225c5-573">Configuration</span></span>

<span data-ttu-id="225c5-p167">Динамический агент группы ответа можно настроить в соответствии с личными предпочтениями с помощью диалогового окна Options (Параметры) приложения. Кроме того, администратор может определить адрес узла по умолчанию, изменив свойство defaultHostAddress в файле RGAgentLive.exe.config.</span><span class="sxs-lookup"><span data-stu-id="225c5-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>
  
<span data-ttu-id="225c5-p168">На приведенном ниже рисунке показано диалоговое окно Options, с помощью которого агенты могут настраивать адрес узла и сочетания клавиш. Чтобы открыть его, нажмите кнопку Options в правом верхнем углу главного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="225c5-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>
  
![Диалоговое окно параметров Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)
  
<span data-ttu-id="225c5-579">В конфигурации динамического агента группы ответа можно настроить следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="225c5-579">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>
  
- <span data-ttu-id="225c5-580">Адрес узла: это обычно веб-сайта пула полное доменное имя, относящегося к агента домашнего пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-580">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="225c5-581">Адрес службы группы ответа автоматически формируется на основе этой информации (путем добавления соответствующего пути после имени узла).</span><span class="sxs-lookup"><span data-stu-id="225c5-581">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>
    
- <span data-ttu-id="225c5-582">Shortcuts (Сочетания клавиш) — можно настроить сочетания клавиш, используемые для входа и выхода.</span><span class="sxs-lookup"><span data-stu-id="225c5-582">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="225c5-583">Единственное ограничение заключается в том, что оба сочетания клавиш должен содержать ключ «Эмблема Windows» (в дополнение к по крайней мере другой ключ).</span><span class="sxs-lookup"><span data-stu-id="225c5-583">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>
    
- <span data-ttu-id="225c5-584">Start with Windows (Запускать при загрузке Windows) — приложение можно настроить так, чтобы оно запускалось автоматически при загрузке ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="225c5-584">Start with Windows: The application can be configured to start automatically with Windows.</span></span>
    
### <a name="examples"></a><span data-ttu-id="225c5-585">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-585">Examples</span></span>

<span data-ttu-id="225c5-586">На приведенном ниже рисунке показано, как позвонить или отправить мгновенное сообщение другому агенту, щелкнув правой кнопкой мыши контакт в области справа.</span><span class="sxs-lookup"><span data-stu-id="225c5-586">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>
  
![Звонок или отправка сообщения.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)
  
<span data-ttu-id="225c5-588">На приведенном ниже рисунке показано, как в динамическом агенте группы ответа отображается текущее число звонков в очереди и самое долгое время ожидания для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="225c5-588">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>
  
![Просмотр сведений очереди.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)
  
### <a name="summary"></a><span data-ttu-id="225c5-590">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-590">Summary</span></span>

<span data-ttu-id="225c5-591">Агент группы ответа предоставляет такие полезные функции, как быстрый вход и выход, сведения о членстве в группах и базовая статистика в режиме реального времени, которые вне приложения доступны только посредством службы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="225c5-591">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="225c5-592">С помощью инструмента ответа группы агентов Live набора ресурсов Скайп для администраторов Business Server 2015 можно обеспечить их агенты с приложением Windows, которая позволяет выполнять задачи быстрее и графических способом.</span><span class="sxs-lookup"><span data-stu-id="225c5-592">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>
  
## <a name="sefautil"></a><span data-ttu-id="225c5-593">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="225c5-593">SEFAUtil</span></span>
<span data-ttu-id="225c5-594"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-594"></span></span>

<span data-ttu-id="225c5-595">SEFAUtil (дополнительный компонент расширению) — это средство командной строки, которая позволяет Скайп Business Server 2015 communications программного обеспечения администраторам и агенты служба технической поддержки для настройки мелодий делегата, переадресации вызовов, одновременных звонков, Параметры группы общих звонков и группу раскладки звонок от имени Скайп для пользователя Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-595">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="225c5-596">Средство также позволяет администраторам запроса параметров маршрутизации вызовов, опубликованных для определенного пользователя. Средство SEFAUtil администратор может включить или отключить/изменение вызова пересылка или одновременный вызов от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-596">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="225c5-597">Администратор можно указать целевой (в виде SIP URI) или использовать целевой объект, который был опубликован пользователем.</span><span class="sxs-lookup"><span data-stu-id="225c5-597">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="225c5-598">Это средство также позволяет администраторам добавлять или удалять делегатов или членов группы общих звонков от имени пользователя. Это средство построения на Microsoft Unified Communications управляемых API (UCMA) 3.0 и необходимо создать доверенное приложение, чтобы администраторы в центральном хранилище управления для SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="225c5-598">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>
  
<span data-ttu-id="225c5-599">SEFAUtil (дополнительный компонент расширению) позволяет Скайп для администраторов Business Server 2015 и служба технической поддержки агенты, для настройки мелодий делегата, переадресации вызовов, одновременных звонков, приема звонков параметры и групповой раскладки звонок от имени Скайп для пользователя Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-599">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="225c5-600">Оно также позволяет администраторам запрашивать параметры маршрутизации звонков, опубликованные для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-600">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-601">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-601">Description</span></span>

<span data-ttu-id="225c5-602">Текущая версия SEFAUtil — только программа командной строки; Нет, не поддерживающей графический интерфейс пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-602">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="225c5-603">Это средство основано на Microsoft Unified Communications управляемых API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="225c5-603">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="225c5-604">Функции в этой программы Разрешить администраторам и агенты служба технической поддержки, выполните следующие:</span><span class="sxs-lookup"><span data-stu-id="225c5-604">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>
  
- <span data-ttu-id="225c5-605">просматривать все параметры маршрутизации звонков для пользователя (включая параметры переадресации звонков, делегирования, одновременных звонков, групповых звонков и группового ответа на звонки);</span><span class="sxs-lookup"><span data-stu-id="225c5-605">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>
    
- <span data-ttu-id="225c5-606">включать, отключать и изменять параметры переадресации звонков (включая назначение и таймер ожидания ответа);</span><span class="sxs-lookup"><span data-stu-id="225c5-606">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>
    
- <span data-ttu-id="225c5-607">включать, отключать и изменять непосредственные конфигурации переадресации звонков;</span><span class="sxs-lookup"><span data-stu-id="225c5-607">Enable/disable/modify call-forwarding immediate configurations</span></span>
    
- <span data-ttu-id="225c5-608">включать, отключать и изменять параметры делегирования;</span><span class="sxs-lookup"><span data-stu-id="225c5-608">Enable/disable/modify delegation settings</span></span>
    
- <span data-ttu-id="225c5-609">включать, отключать и изменять параметры группы приема звонков;</span><span class="sxs-lookup"><span data-stu-id="225c5-609">Enable/disable/modify team-call group settings</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="225c5-610">Новые возможности Скайп средством Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="225c5-610">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
- <span data-ttu-id="225c5-611">включать, отключать и изменять параметры одновременных звонков (включая назначение);</span><span class="sxs-lookup"><span data-stu-id="225c5-611">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="225c5-612">Новые возможности Скайп средством Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="225c5-612">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
- <span data-ttu-id="225c5-613">включать, отключать и изменять параметры группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="225c5-613">Enable/disable/modify group call pickup settings</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="225c5-614">Новые возможности Скайп средством Business Server 2015 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="225c5-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span> 
  
<span data-ttu-id="225c5-615">В отношении средства действуют перечисленные ниже ограничения.</span><span class="sxs-lookup"><span data-stu-id="225c5-615">This tool has the following limitations:</span></span>
  
- <span data-ttu-id="225c5-616">Поддерживается только для пользователей, размещенных в Скайп для пула Business Server</span><span class="sxs-lookup"><span data-stu-id="225c5-616">Supported only for users homed in a Skype for Business Server pool</span></span>
    
- <span data-ttu-id="225c5-617">Групповое изменение параметров маршрутизации звонков для нескольких пользователей не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="225c5-617">Bulk-edit of call routing settings for several users is not supported</span></span>
    
### <a name="output"></a><span data-ttu-id="225c5-618">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-618">Output</span></span>

<span data-ttu-id="225c5-p175">В текущей версии средства данные выводятся только в окне командной строки. Подробные сведения см. в разделе «Примеры» далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="225c5-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="225c5-621">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-621">Purpose</span></span>

<span data-ttu-id="225c5-622">Ниже приведены некоторые основные сценарии, в которых можно использовать это средство.</span><span class="sxs-lookup"><span data-stu-id="225c5-622">Following are some of the key scenarios where this tool may be used:</span></span>
  
- <span data-ttu-id="225c5-623">Боб является руководителем и перемещена в Скайп для телефонии Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-623">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="225c5-624">Он имеет делегирования на свой существующая система УАТС.</span><span class="sxs-lookup"><span data-stu-id="225c5-624">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="225c5-625">Как часть переход на Скайп для Business Server 2015 администратор имеет возможность настройки Bob маршрутизации в соответствии с уже существующей конфигурацию и делегирования.</span><span class="sxs-lookup"><span data-stu-id="225c5-625">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>
    
- <span data-ttu-id="225c5-p177">Юлия находится в командировке и должна получить важный звонок от одного из клиентов. Однако она находится в гостинице и не имеет доступа к компьютеру. Юлия звонит в службу технической поддержки и просит, чтобы все звонки на ее рабочий номер переадресовывались на номер мобильного телефона. Специалисты службы поддержки производят настройку от ее имени.</span><span class="sxs-lookup"><span data-stu-id="225c5-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>
    
- <span data-ttu-id="225c5-630">Будет Джо звонков на свой рабочий номер своего мобильного голосовой почты каждый раз, когда он находится на работе; Тем не менее все выглядит правильно работать в других местах.</span><span class="sxs-lookup"><span data-stu-id="225c5-630">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="225c5-631">Техника служба технической поддержки доступны для просмотра конфигурации маршрутизации Джо и обнаруживает, что Иван имеет одновременных звонков, настроенных на свой мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="225c5-631">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="225c5-632">Технического специалиста указываются Джо мобильных покрытия на свой office и может определить, что одновременных звонков правила является причину вызывает переход на мобильных Джо голосовой почты при его покрытия сети очень медленно.</span><span class="sxs-lookup"><span data-stu-id="225c5-632">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>
    
- <span data-ttu-id="225c5-633">Майк новых сотрудников в компании Contoso и он присоединения к собранию — новой группы, на котором все члены настроены для приема звонков, при включаемого для Скайп для Business Server 2015, администратор имеет возможность задать параметры группы для включения всех членов группы, его нового его группы приема звонков , кроме того, администратор добавляет Майк в качестве члена группы приема звонков для каждого из участников в его группы.</span><span class="sxs-lookup"><span data-stu-id="225c5-633">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>
    
- <span data-ttu-id="225c5-634">В отделе кадров компании Contoso все абоненты обслуживаются специалистами с первого звонка.</span><span class="sxs-lookup"><span data-stu-id="225c5-634">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="225c5-635">При групповых звонках все телефоны звонят одновременно, что отвлекает сотрудников отдела от работы.</span><span class="sxs-lookup"><span data-stu-id="225c5-635">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="225c5-636">Для предоставления услуг без нарушения работы участников группы, Скайп для администратора Business Server 2015 использует возможность вызова раскладки группы.</span><span class="sxs-lookup"><span data-stu-id="225c5-636">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="225c5-637">Он добавляет всех сотрудников отдела в группу ответа и сообщает им номер этой группы.</span><span class="sxs-lookup"><span data-stu-id="225c5-637">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="225c5-638">Когда Светланы нет на рабочем месте, Алексей, замечая, что ее телефон звонит, может ответить на звонок со своего рабочего места.</span><span class="sxs-lookup"><span data-stu-id="225c5-638">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="225c5-639">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-639">Requirements</span></span>

<span data-ttu-id="225c5-p180">Средство SEFAUtil можно запускать только на компьютере, входящем в пул доверенных приложений. На этом компьютере должен быть установлен интерфейс UCMA 3.0. Для запуска средства в пуле необходимо создать доверенное приложение с идентификатором приложения SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="225c5-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>
  
### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="225c5-643">Создание доверенного приложения для средства SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="225c5-643">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="225c5-644">Средство SEFAUTil может выполняться только на компьютере, который является частью пула доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="225c5-644">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="225c5-645">При необходимости добавления в пул в качестве нового пула доверенных приложений можно выполнить с помощью Скайп для консоли Business Server с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="225c5-645">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>
    
  ```
  New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
  ```

    > [!NOTE]
    > <span data-ttu-id="225c5-646">Интерфейс UCMA 3.0 нужно установить на всех компьютерах, на которых будет запускаться средство SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="225c5-646">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span> 
  
2. <span data-ttu-id="225c5-647">Доверенное приложение должен быть определен в топологии для средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="225c5-647">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="225c5-648">Определение SEFAUtil в качестве нового доверенного приложения, используйте Скайп для Business Server Командная консоль и выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="225c5-648">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span> 
    
  ```
  New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
  ```

    > [!NOTE]
    > <span data-ttu-id="225c5-649">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="225c5-649">A different port can be used if needed.</span></span> 
  
3. <span data-ttu-id="225c5-650">Изменения топологии необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="225c5-650">The topology changes need to be enabled.</span></span> <span data-ttu-id="225c5-651">Включение изменения топологии можно выполнить с помощью Скайп для консоли Business Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="225c5-651">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span> 
    
  ```
  Enable-CsToplogy
  ```

4. <span data-ttu-id="225c5-652">При необходимости установите Скайп для Business Server 2015 Resource Kit Tools на сервере, который будет использоваться для запуска инструмента SEFAUtil (сервер должен быть частью пула доверенных приложений).</span><span class="sxs-lookup"><span data-stu-id="225c5-652">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>
    
5. <span data-ttu-id="225c5-653">Убедитесь в том, что средство SEFAUtil работает правильно.</span><span class="sxs-lookup"><span data-stu-id="225c5-653">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="225c5-654">Для этого запустите его из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="225c5-654">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="225c5-655">По умолчанию средство размещаются в: «...\Program Files\Skype для 2015\Reskit Business Server».</span><span class="sxs-lookup"><span data-stu-id="225c5-655">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="225c5-656">Чтобы вывести на экран параметры переадресации звонков пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="225c5-656">To display the call forwarding settings of a user, use the following command:</span></span> 
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
  ```

    <span data-ttu-id="225c5-657">На экране должны появиться параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-657">The call forwarding settings of the user should be displayed.</span></span>
    
#### <a name="group-call-pickup"></a><span data-ttu-id="225c5-658">Групповой ответ на звонки</span><span class="sxs-lookup"><span data-stu-id="225c5-658">Group Call Pickup</span></span>

<span data-ttu-id="225c5-659">Групповой звонок раскладки требуется дополнительная настройка в Скайп для Business Server 2015 возможности полностью необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="225c5-659">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="225c5-660">Перед тем как назначать группы ответа пользователям, обратитесь к документации по функции группового ответа на звонки, чтобы получить инструкции по ее планированию и развертыванию.</span><span class="sxs-lookup"><span data-stu-id="225c5-660">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-661">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-661">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="225c5-662">Отображение текущих параметров обработки звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-662">Display Current Call Handling Settings</span></span>

<span data-ttu-id="225c5-663">Следующая команда выводит параметры обработки звонков для пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-663">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`
  
> [!NOTE]
> <span data-ttu-id="225c5-664">В этом примере используется **параметр/Server** для указания Скайп для Business Server для подключения.</span><span class="sxs-lookup"><span data-stu-id="225c5-664">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>
  
 <span data-ttu-id="225c5-665">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-665">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="225c5-666">Задание назначения для переадресации звонков и неотвеченных звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-666">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="225c5-667">В этом примере задается назначения ответов прямого/нет вызовов и задержка звонка.</span><span class="sxs-lookup"><span data-stu-id="225c5-667">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="225c5-668">Здесь не указан параметр/Server; SEFAUtil предпринимается попытка автоматического обнаружения Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-668">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="225c5-669">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-669">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="225c5-670">Немедленное включение переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-670">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="225c5-671">В этом примере немедленно включается переадресация звонков другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="225c5-671">This example immediately enables call-forwarding to another user.</span></span>
  
```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="225c5-672">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-672">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="225c5-673">Немедленное отключение переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-673">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="225c5-674">В этом примере немедленно отключается переадресация звонков.</span><span class="sxs-lookup"><span data-stu-id="225c5-674">This example immediately disables call forwarding.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="225c5-675">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-675">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="225c5-676">Добавление пользователя в качестве делегата и настройка одновременных звонков делегатам</span><span class="sxs-lookup"><span data-stu-id="225c5-676">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="225c5-677">В этом примере пользователь добавляется в качестве делегата и настраиваются одновременные звонки делегатам.</span><span class="sxs-lookup"><span data-stu-id="225c5-677">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="225c5-678">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-678">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="225c5-679">Изменение правила одновременных звонков делегатам</span><span class="sxs-lookup"><span data-stu-id="225c5-679">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="225c5-680">В этом примере правило одновременных звонков, настроенное в предыдущем примере, изменяется на правило задержки звонков.</span><span class="sxs-lookup"><span data-stu-id="225c5-680">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="225c5-681">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-681">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="225c5-682">Удаление делегата</span><span class="sxs-lookup"><span data-stu-id="225c5-682">Remove the Delegate</span></span>

<span data-ttu-id="225c5-683">В этом примере удаляется делегат.</span><span class="sxs-lookup"><span data-stu-id="225c5-683">This example removes the delegate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="225c5-684">После удаления последнего делегата делегированные звонки автоматически отключаются.</span><span class="sxs-lookup"><span data-stu-id="225c5-684">When the last delegate is removed, delegate ringing is automatically disabled.</span></span> 
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="225c5-685">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-685">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="225c5-686">Добавление делегата и настройка правила переадресации звонков делегатам</span><span class="sxs-lookup"><span data-stu-id="225c5-686">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="225c5-687">В этом примере добавляется делегат и настраивается правило переадресации звонков делегатам.</span><span class="sxs-lookup"><span data-stu-id="225c5-687">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="225c5-688">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-688">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="225c5-689">Включение одновременных звонков и задание номера назначения</span><span class="sxs-lookup"><span data-stu-id="225c5-689">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="225c5-690">В этом примере включаются одновременные звонки и задается номер назначения для них.</span><span class="sxs-lookup"><span data-stu-id="225c5-690">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="225c5-691">Чтобы изменить номер назначения одновременных звонков для пользователя, для которого уже включены одновременные звонки, используйте в команде параметр /enablesimulring. В противном случае номер назначения не изменится.</span><span class="sxs-lookup"><span data-stu-id="225c5-691">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span> 
  
 <span data-ttu-id="225c5-692">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-692">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="225c5-693">Отключение одновременных звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-693">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="225c5-694">В этом примере отключаются одновременные звонки.</span><span class="sxs-lookup"><span data-stu-id="225c5-694">This example disables simultaneous ringing.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="225c5-695">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-695">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="225c5-696">Добавление пользователя в группу приема звонков и настройка одновременных звонков группе приема звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-696">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="225c5-697">В этом примере добавляется член группы приема звонков и включаются одновременные звонки этой группе.</span><span class="sxs-lookup"><span data-stu-id="225c5-697">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="225c5-698">При добавлении члена в группу приема звонков пользователя параметры одновременных звонков автоматически изменяются на выполнение одновременных звонков в эту группу.</span><span class="sxs-lookup"><span data-stu-id="225c5-698">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span> 
  
 <span data-ttu-id="225c5-699">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-699">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="225c5-700">Удаление члена из группы приема звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-700">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="225c5-701">В этом примере удаляется один из членов группы приема звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-701">This example removes a team member of the team-call group of a user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="225c5-702">Если удаляемый член является единственным в группе приема звонков, одновременные звонки группе приема звонков автоматически отключаются.</span><span class="sxs-lookup"><span data-stu-id="225c5-702">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span> 
  
 <span data-ttu-id="225c5-703">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-703">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="225c5-704">Настройка задержки звонков в группу приема звонков</span><span class="sxs-lookup"><span data-stu-id="225c5-704">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="225c5-705">В этом примере изменяется параметр задержки звонков в группу приема звонков.</span><span class="sxs-lookup"><span data-stu-id="225c5-705">This example changes the delayed ring to the team-call group time setting.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="225c5-706">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-706">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="225c5-707">Включение группового звонка</span><span class="sxs-lookup"><span data-stu-id="225c5-707">Enable Team-Call</span></span>

<span data-ttu-id="225c5-708">В этом примере включается групповой звонок для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-708">This example enables team-call for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="225c5-709">Если группы приема звонков пользователя, не имеет членов, не будут включены приема звонков.</span><span class="sxs-lookup"><span data-stu-id="225c5-709">If the team-call group of the user has no members, team-call won't be enabled.</span></span> 
  
 <span data-ttu-id="225c5-710">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-710">**Output**</span></span>
  
#### <a name="disable-team-call"></a><span data-ttu-id="225c5-711">Отключение группового звонка</span><span class="sxs-lookup"><span data-stu-id="225c5-711">Disable Team-Call</span></span>

<span data-ttu-id="225c5-712">В этом примере отключается групповой звонок для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-712">This example disables team-call for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="225c5-713">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-713">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="225c5-714">Включение группового ответа на звонки и назначение группы ответа пользователю</span><span class="sxs-lookup"><span data-stu-id="225c5-714">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="225c5-715">В этом примере пользователю назначается группа ответа и включается групповой ответ на звонки.</span><span class="sxs-lookup"><span data-stu-id="225c5-715">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="225c5-716">**Выходные данные**</span><span class="sxs-lookup"><span data-stu-id="225c5-716">**Output**</span></span>
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="225c5-717">Отключение группового ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="225c5-717">Disable Group Call Pickup</span></span>

<span data-ttu-id="225c5-718">В этом примере отключается групповой ответ на звонки для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-718">This example disables Group Call Pickup for a given user.</span></span>
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="225c5-p187">Когда вы отключаете функцию группового ответа на звонки для пользователя, номер группы, который был назначен пользователю, не сохраняется. Если вы впоследствии повторно включаете функцию группового ответа на звонки для данного пользователя, необходимо снова назначить номер группы с помощью параметра /enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="225c5-p187">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span> 
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="225c5-721">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="225c5-721">SYSPrep.ps1</span></span>
<span data-ttu-id="225c5-722"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-722"></span></span>

### <a name="description"></a><span data-ttu-id="225c5-723">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-723">Description</span></span>

<span data-ttu-id="225c5-724">SYSPrep.ps1 — это сценарий Windows PowerShell, предназначенным для установки следующих Скайп наличие необходимых компонентов Business Server 2015 на компьютере операционной системы Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="225c5-724">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>
  
- <span data-ttu-id="225c5-725">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="225c5-725">Microsoft .Net Framework 4.5</span></span>
    
- <span data-ttu-id="225c5-726">Microsoft SQL Server, экспресс-выпуск</span><span class="sxs-lookup"><span data-stu-id="225c5-726">Microsoft SQL Server Express</span></span>
    
- <span data-ttu-id="225c5-727">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="225c5-727">Windows Powershell version 3.0</span></span>
    
- <span data-ttu-id="225c5-728">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="225c5-728">Visual C++ 2010 Redistributable</span></span>
    
- <span data-ttu-id="225c5-729">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="225c5-729">Internet Information Server Updates</span></span>
    
- <span data-ttu-id="225c5-730">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="225c5-730">Windows Identity Foundation</span></span>
    
- <span data-ttu-id="225c5-731">Скайп для Business Server 2015 основные файлы</span><span class="sxs-lookup"><span data-stu-id="225c5-731">Skype for Business Server 2015 Core files</span></span>
    
 <span data-ttu-id="225c5-732">Хотя имя этого сценария совпадает с именем средства SysPrep для операционных систем Microsoft Windows, эти средства отличаются.</span><span class="sxs-lookup"><span data-stu-id="225c5-732">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="225c5-733">Этот сценарий только установит необходимые условия для Скайп Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-733">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="225c5-734">После установки этих компонентов можно создать образ сервера с помощью средства SysPrep Windows.</span><span class="sxs-lookup"><span data-stu-id="225c5-734">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>
  
### <a name="requirements"></a><span data-ttu-id="225c5-735">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-735">Requirements</span></span>

<span data-ttu-id="225c5-736">Перед запуском сценария SYSPrep.ps1 необходимо скопировать необходимые файлы в локальную папку на компьютере операционной системы Windows Server 2008 (например **D:\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="225c5-736">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="225c5-737">Эта папка должен также включать копию Скайп для файлов, Business Server 2015, в частности **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="225c5-737">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="225c5-738">Файлы необходимых компонентов можно загрузить на следующих страницах.</span><span class="sxs-lookup"><span data-stu-id="225c5-738">The prerequisite files can be downloaded from the following locations:</span></span>
  
|<span data-ttu-id="225c5-739">**Необходимые компоненты**</span><span class="sxs-lookup"><span data-stu-id="225c5-739">**Prerequisite**</span></span>|<span data-ttu-id="225c5-740">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="225c5-740">**Location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="225c5-741">Microsoft .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="225c5-741">Microsoft .Net Framework 4.5</span></span>  <br/> |http://go.microsoft.com/?linkid=9816306  <br/> |
|<span data-ttu-id="225c5-742">Microsoft SQL Server 2008 R2, экспресс-выпуск</span><span class="sxs-lookup"><span data-stu-id="225c5-742">Microsoft SQL Server Express 2008 R2</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=23650  <br/> |
|<span data-ttu-id="225c5-743">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="225c5-743">Windows Powershell version 3.0</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34595  <br/> |
|<span data-ttu-id="225c5-744">Распространяемый пакет Visual C++ 2010</span><span class="sxs-lookup"><span data-stu-id="225c5-744">Visual C++ 2010 Redistributable</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=5555  <br/> |
|<span data-ttu-id="225c5-745">Обновления для сервера IIS</span><span class="sxs-lookup"><span data-stu-id="225c5-745">Internet Information Server Updates</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34869  <br/> |
|<span data-ttu-id="225c5-746">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="225c5-746">Windows Identity Foundation</span></span>  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=17331  <br/> |
|<span data-ttu-id="225c5-747">Скайп для Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="225c5-747">Skype for Business Server 2015 Setup.exe</span></span>  <br/> |<span data-ttu-id="225c5-748">Копировать из Скайп Business Server 2015 мультимедиа</span><span class="sxs-lookup"><span data-stu-id="225c5-748">Copy from Skype for Business Server 2015 media</span></span>  <br/> |
   
### <a name="parameter"></a><span data-ttu-id="225c5-749">Параметр</span><span class="sxs-lookup"><span data-stu-id="225c5-749">Parameter</span></span>

<span data-ttu-id="225c5-750">Параметр **- SetupFolder** принимает в качестве аргумента расположение каталога необходимых компонентов</span><span class="sxs-lookup"><span data-stu-id="225c5-750">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-751">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-751">Examples</span></span>

<span data-ttu-id="225c5-752">Чтобы запустить сценарий SYSPrep.ps1 и установить Скайп наличие необходимых компонентов Business Server 2015, выполните следующую команду из командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="225c5-752">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>
  
```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="225c5-753">Перенос оповещений о неназначенных номерах</span><span class="sxs-lookup"><span data-stu-id="225c5-753">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="225c5-754"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-754"></span></span>

<span data-ttu-id="225c5-755">Средство миграции извещения неназначенный номер позволяет Скайп Business Server 2015 администратора для настройки неназначенных номеров, который обслуживается объявлений приложения из источника Скайп для Business Server или пула для перемещения Назначение Скайп Business Server или пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-755">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-756">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-756">Description</span></span>

<span data-ttu-id="225c5-757">Средство переноса оповещений о неназначенных номерах — это сценарий Windows PowerShell, который перемещает конфигурацию неназначенных номеров, обслуживаемую приложением «Оповещение», с исходного сервера (или пула) на другой.</span><span class="sxs-lookup"><span data-stu-id="225c5-757">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>
  
<span data-ttu-id="225c5-758">При запуске сценарий переноса оповещений о неназначенных номерах выполняет следующие операции.</span><span class="sxs-lookup"><span data-stu-id="225c5-758">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>
  
1. <span data-ttu-id="225c5-759">Переносит все звуковые файлы, которые используются оповещениями о неназначенных номерах в приложении «Оповещение», размещенном на исходном сервере или в исходном пуле, в хранилище файлов конечного сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-759">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="225c5-760">Звуковые файлы удаляются из исходный пул, как только они будут скопированы в конечном пуле.</span><span class="sxs-lookup"><span data-stu-id="225c5-760">The audio files are removed from the source pool once they're copied to the destination pool.</span></span> 
  
2. <span data-ttu-id="225c5-761">Переносит все оповещения о неназначенных номерах, которые настроены для приложения «Оповещение», размещенного на исходном сервере или в исходном пуле, на конечный сервер или в конечный пул.</span><span class="sxs-lookup"><span data-stu-id="225c5-761">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>
    
3. <span data-ttu-id="225c5-762">Переназначает все диапазоны неназначенных номеров, которые обслуживаются приложением «Оповещение», размещенным на исходном сервере или в исходном пуле, конечному серверу или пулу.</span><span class="sxs-lookup"><span data-stu-id="225c5-762">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>
    
<span data-ttu-id="225c5-763">После успешного выполнения сценария все диапазоны неназначенных номеров, которые обслуживались приложением «Оповещение», размещенным на исходном сервере или в исходном пуле, будут обслуживаться конечным сервером или пулом с сохранением конфигурации.</span><span class="sxs-lookup"><span data-stu-id="225c5-763">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>
  
### <a name="output"></a><span data-ttu-id="225c5-764">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-764">Output</span></span>

<span data-ttu-id="225c5-765">Указывает сценария **Move-CsAnnouncementConfiguration** в Скайп, для которой оно выполнено успешное или неудачное выполнение операции переноса в окне консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-765">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>
  
<span data-ttu-id="225c5-p190">Если выполнение операции было прервано в результате ошибки, успешно перенесенные диапазоны неназначенных номеров останутся на конечном сервере или в конечном пуле и будут работоспособны, а остальные диапазоны останутся на исходном сервере или в исходном пуле и также будут работоспособны. Чтобы полностью перенести конфигурацию, устраните причину ошибки и повторно запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="225c5-p190">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>
  
### <a name="purpose"></a><span data-ttu-id="225c5-768">Назначение</span><span class="sxs-lookup"><span data-stu-id="225c5-768">Purpose</span></span>

<span data-ttu-id="225c5-769">Сценарий переноса оповещений о неназначенных номерах можно использовать в следующих трех сценариях.</span><span class="sxs-lookup"><span data-stu-id="225c5-769">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>
  
- <span data-ttu-id="225c5-770">**Параметры конфигурации миграция на новую версию Скайп для Business Server:** Contoso — в процессе миграции в Скайп for Business Server 2015 и в ходе процесса миграции Скайп для Business Server администратор хочет перемещение настройки неназначенных номеров, обслуживаемых приложением объявлений из Lync Развертывание Server 2013 для нового Скайп для развертывания Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-770">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="225c5-771">Чтобы переместить параметры конфигурации, Скайп для администратора Business Server использует средства переноса извещения неназначенный номер.</span><span class="sxs-lookup"><span data-stu-id="225c5-771">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>
    
- <span data-ttu-id="225c5-772">**Откат развертывания в Скайп для Business Server 2015 на Lync Server 2013:** Из-за непредвиденных последствий Contoso должен откат миграции для нового Скайп для развертывания Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="225c5-772">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="225c5-773">Для сведения к минимуму перерывы в службе, Скайп для администратора Business Server использует средства переноса извещения неназначенный номер выполнить откат конфигурации из Скайп для развертывания Business Server 2015 по отношению к развертыванию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="225c5-773">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>
    
- <span data-ttu-id="225c5-774">**Перемещение данных между развертываний:** Contoso — в процессе замена всех серверов из одного пула на новые серверы.</span><span class="sxs-lookup"><span data-stu-id="225c5-774">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="225c5-775">Их стратегия предназначена для развертывания нового Скайп для пула Business Server 2015 переместить все данные из старого в новый пул, а затем отказаться от старого пула.</span><span class="sxs-lookup"><span data-stu-id="225c5-775">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="225c5-776">После развертывания нового пула конфигурация переносится из старого пула в новый с помощью средства переноса оповещений о неназначенных номерах.</span><span class="sxs-lookup"><span data-stu-id="225c5-776">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>
    
#### <a name="requirements"></a><span data-ttu-id="225c5-777">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-777">Requirements</span></span>

<span data-ttu-id="225c5-778">Для успешной работы средства должны выполняться перечисленные ниже основные требования.</span><span class="sxs-lookup"><span data-stu-id="225c5-778">The following are the main requirements needed to successfully run the tool:</span></span>
  
1. <span data-ttu-id="225c5-779">Необходимо выполнить скрипт в компьютер с Скайп установлена командная консоль Business Server.</span><span class="sxs-lookup"><span data-stu-id="225c5-779">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>
    
2. <span data-ttu-id="225c5-780">Приложение оповещения имеет для успешного развертывания в исходном и целевом Скайп для бизнеса серверов или пулов.</span><span class="sxs-lookup"><span data-stu-id="225c5-780">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>
    
#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="225c5-781">Сценарий Move-CsAnnouncementConfiguration</span><span class="sxs-lookup"><span data-stu-id="225c5-781">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="225c5-782">Сценарий Move-CsAnnouncementConfiguration требует использования двух параметров, которые описаны в таблице ниже. </span><span class="sxs-lookup"><span data-stu-id="225c5-782">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span> 
  
![Параметры Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)
  
### <a name="examples"></a><span data-ttu-id="225c5-784">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-784">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="225c5-785">Перемещение неназначенных номеров конфигурации объявлений из пула Lync Server 2013 Скайп Business Server 2015 пула</span><span class="sxs-lookup"><span data-stu-id="225c5-785">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="225c5-786">В этом примере перемещает неназначенных номеров объявлений из исходный пул (Lync Server 2013) в целевом пуле (Скайп для Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="225c5-786">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>
  
```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com

```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="225c5-787">Перемещение неназначенных номеров конфигурации объявлений из Скайп для пула сервера 2015 Business пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="225c5-787">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="225c5-788">В этом примере перемещает неназначенных номеров объявлений из исходный пул (Скайп для Business Server 2015) в целевом пуле (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="225c5-788">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>
  
```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="225c5-789">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="225c5-789">Web Conf Data</span></span>
<span data-ttu-id="225c5-790"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="225c5-790"></span></span>

<span data-ttu-id="225c5-791">Веб-средство данных Conf администратор Скайп для программного обеспечения Business Server 2015 иметь лучше контролировать данные, связанные с организатора веб-конференции.</span><span class="sxs-lookup"><span data-stu-id="225c5-791">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="225c5-792">Сценарии включают возможность удаления данных собрания определенного пользователя на основе критериев отметок времени.</span><span class="sxs-lookup"><span data-stu-id="225c5-792">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>
  
### <a name="description"></a><span data-ttu-id="225c5-793">Описание</span><span class="sxs-lookup"><span data-stu-id="225c5-793">Description</span></span>

<span data-ttu-id="225c5-794">Это средство позволяет администратору выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="225c5-794">This tool allows the administrator to perform the following operations:</span></span>
  
1. <span data-ttu-id="225c5-795">находить все данные веб-конференций, связанные с отдельным пользователем;</span><span class="sxs-lookup"><span data-stu-id="225c5-795">Find all Web conferencing data associated with a single user.</span></span>
    
2. <span data-ttu-id="225c5-796">удалять все данные веб-конференций, связанные с отдельным пользователем;</span><span class="sxs-lookup"><span data-stu-id="225c5-796">Delete all Web conferencing data associated with a single user.</span></span>
    
3. <span data-ttu-id="225c5-797">удалять все данные веб-конференций, связанные с отдельным пользователем, старше определенной даты;</span><span class="sxs-lookup"><span data-stu-id="225c5-797">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>
    
4. <span data-ttu-id="225c5-798">переносить все данные веб-конференций, связанные с отдельным пользователем, если этот пользователь переносится из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="225c5-798">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>
    
> [!NOTE]
> <span data-ttu-id="225c5-799">Средства набора ресурсов для Lync Server 2010 поддерживается перемещение всех веб-конференций данных, связанных с одним пользователем, при перемещении пользователя из одного пула в другой.</span><span class="sxs-lookup"><span data-stu-id="225c5-799">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="225c5-800">Такая функциональная возможность рекомендуется из этого инструмента пользу параметр **MoveConferenceData** .</span><span class="sxs-lookup"><span data-stu-id="225c5-800">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="225c5-801">Для получения дополнительных сведений об этом параметре видеть командлета [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="225c5-801">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>
  
<span data-ttu-id="225c5-p196">Средство удаляет данные только для неактивных собраний. Активные собрания (или собрания в рамках сеансов) удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="225c5-p196">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>
  
<span data-ttu-id="225c5-p197">Это средство необходимо запускать на компьютере, который входит в тот же пул, что и целевой пользователь. Пользователь, для управления данными собраний которого используется это средство, должен быть размещен в том же пуле пользователей.</span><span class="sxs-lookup"><span data-stu-id="225c5-p197">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>
  
### <a name="output"></a><span data-ttu-id="225c5-806">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="225c5-806">Output</span></span>

<span data-ttu-id="225c5-807">Средство выводит результаты каждой операции.</span><span class="sxs-lookup"><span data-stu-id="225c5-807">This tool outputs the results of each of the operations:</span></span>
  
- <span data-ttu-id="225c5-808">Если выполняется запрос, средство выводит список всех папок с данными неактивных собраний, организатором которых является указанный пользователь.</span><span class="sxs-lookup"><span data-stu-id="225c5-808">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>
    
- <span data-ttu-id="225c5-809">Если выполняется удаление, средство выводит список всех папок с данными собраний, которые будут удалены.</span><span class="sxs-lookup"><span data-stu-id="225c5-809">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>
    
### <a name="requirements"></a><span data-ttu-id="225c5-810">Требования</span><span class="sxs-lookup"><span data-stu-id="225c5-810">Requirements</span></span>

<span data-ttu-id="225c5-811">Средство необходимо запускать в том же пуле, в котором в настоящее время размещен организатор.</span><span class="sxs-lookup"><span data-stu-id="225c5-811">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>
  
<span data-ttu-id="225c5-812">Средство должно запускаться с правами администратора на доступ к хранилищу файлов содержимого.</span><span class="sxs-lookup"><span data-stu-id="225c5-812">The tool must be run using administrator privileges with access to the Content File Store.</span></span>
  
### <a name="examples"></a><span data-ttu-id="225c5-813">Примеры</span><span class="sxs-lookup"><span data-stu-id="225c5-813">Examples</span></span>

<span data-ttu-id="225c5-814">В приведенной ниже таблице описываются параметры, некоторые из которых используются в примерах.</span><span class="sxs-lookup"><span data-stu-id="225c5-814">The following table describes the parameters, some of which are used in the examples.</span></span>
  
![Параметры Web Conf Data Tool.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="225c5-p198">В предыдущем примере показано, как выполняется команда запроса. Выходные данные этой команды представляют собой список всех папок с содержимым собраний, которые будут затронуты при работе средства.</span><span class="sxs-lookup"><span data-stu-id="225c5-p198">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="225c5-p199">Выше приведен пример команды удаления. Она удаляет все папки неактивных собраний для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="225c5-p199">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>
  
### <a name="summary"></a><span data-ttu-id="225c5-820">Сводка</span><span class="sxs-lookup"><span data-stu-id="225c5-820">Summary</span></span>

<span data-ttu-id="225c5-821">Это средство может быть ценным ресурсом для администраторов, которым требуется более полный контроль над данными конференций.</span><span class="sxs-lookup"><span data-stu-id="225c5-821">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>
  

