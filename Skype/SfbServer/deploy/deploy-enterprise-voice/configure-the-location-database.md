---
title: Настройка базы данных местоположений в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Настройте, заполните и опубликуйте базу данных расположения E9-1-1 в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 4b8848637130886250d08847c45df3c2dc080f5b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768112"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="9a42e-103">Настройка базы данных местоположений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9a42e-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="9a42e-104">Настройте, заполните и опубликуйте базу данных расположения E9-1-1 в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9a42e-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="9a42e-105">Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="9a42e-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="9a42e-106">Чтобы настроить базу данных местоположений, следует выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="9a42e-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="9a42e-107">Заполните базу данных с сопоставлением сетевых элементов местоположениям.</span><span class="sxs-lookup"><span data-stu-id="9a42e-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="9a42e-108">При использовании шлюза идентификационный номер места для экстренного реагирования (Елин) необходимо добавить Елин в поле \<CompanyName\> .</span><span class="sxs-lookup"><span data-stu-id="9a42e-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="9a42e-109">Если вы не заполняете базу данных расположений, и для параметра **Требуется местоположение** в политике местоположений задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.</span><span class="sxs-lookup"><span data-stu-id="9a42e-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="9a42e-110">Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="9a42e-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="9a42e-111">Опубликуйте обновленную базу данных.</span><span class="sxs-lookup"><span data-stu-id="9a42e-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="9a42e-112">Наполнение базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="9a42e-112">Populate the location database</span></span>

<span data-ttu-id="9a42e-113">Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в карте географических соответствий, которая сопоставляет элементы сети с городскими адресами (например, улицей).</span><span class="sxs-lookup"><span data-stu-id="9a42e-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="9a42e-114">Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.</span><span class="sxs-lookup"><span data-stu-id="9a42e-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="9a42e-115">Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9a42e-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="9a42e-p103">Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="9a42e-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="9a42e-118">**Элемент сети**</span><span class="sxs-lookup"><span data-stu-id="9a42e-118">**Network Element**</span></span>|<span data-ttu-id="9a42e-119">**Обязательные столбцы**</span><span class="sxs-lookup"><span data-stu-id="9a42e-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a42e-120">**Точка беспроводного доступа**</span><span class="sxs-lookup"><span data-stu-id="9a42e-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="9a42e-121">\<BSSID\>,\<Описание\>,\<расположение\>,\<CompanyName\>,\<хаусенумбер\>,\<хаусенумберсуффикс\>,\<преднаправленный\>,...</span><span class="sxs-lookup"><span data-stu-id="9a42e-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9a42e-122">... \<Стритнаме\>,\<стритсуффикс\>,\<\>i Direction\<, City\>,\<штат\>,\<PostalCode\>, страна\<\></span><span class="sxs-lookup"><span data-stu-id="9a42e-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9a42e-123">**Subnet**</span><span class="sxs-lookup"><span data-stu-id="9a42e-123">**Subnet**</span></span> <br/> |<span data-ttu-id="9a42e-124">\<\>Подсеть\<,\>Описание\<,\>расположение\<,\>CompanyName\<,\>хаусенумбер\<,\>хаусенумберсуффикс\<, преднаправленный\>,...</span><span class="sxs-lookup"><span data-stu-id="9a42e-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9a42e-125">... \<Стритнаме\>,\<стритсуффикс\>,\<\>i Direction\<, City\>,\<штат\>,\<PostalCode\>, страна\<\></span><span class="sxs-lookup"><span data-stu-id="9a42e-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9a42e-126">**Порт**</span><span class="sxs-lookup"><span data-stu-id="9a42e-126">**Port**</span></span> <br/> |<span data-ttu-id="9a42e-127">\<Чассисид\>,\<портидсубтипе\>,\<Портид\>,\<Описание\>,\<расположение\>,\<CompanyName\>,\<хаусенумбер\>,\<хаусенумберсуффикс\>,...</span><span class="sxs-lookup"><span data-stu-id="9a42e-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="9a42e-128">... \<Преднаправленный\>,\<стритнаме\>,\<стритсуффикс\>,\<\>двусторонний\<, город\>,\<штат\>,\<PostalCode\>, страна\<\></span><span class="sxs-lookup"><span data-stu-id="9a42e-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9a42e-129">**Коммутатор**</span><span class="sxs-lookup"><span data-stu-id="9a42e-129">**Switch**</span></span> <br/> |<span data-ttu-id="9a42e-130">\<Чассисид\>,\<Описание\>,\<расположение\>,\<CompanyName\>,\<хаусенумбер\>,\<хаусенумберсуффикс\>,\<преднаправленный\>,...</span><span class="sxs-lookup"><span data-stu-id="9a42e-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9a42e-131">... \<Стритнаме\>,\<стритсуффикс\>,\<\>i Direction\<, City\>,\<штат\>,\<PostalCode\>, страна\<\></span><span class="sxs-lookup"><span data-stu-id="9a42e-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="9a42e-132">Добавление элементов сети в базу данных расположений</span><span class="sxs-lookup"><span data-stu-id="9a42e-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="9a42e-133">Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.</span><span class="sxs-lookup"><span data-stu-id="9a42e-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="9a42e-p104">Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:</span><span class="sxs-lookup"><span data-stu-id="9a42e-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="9a42e-137">Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.</span><span class="sxs-lookup"><span data-stu-id="9a42e-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="9a42e-138">Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="9a42e-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="9a42e-139">Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.</span><span class="sxs-lookup"><span data-stu-id="9a42e-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="9a42e-140">Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="9a42e-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="9a42e-141">Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="9a42e-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="9a42e-142">Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="9a42e-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="9a42e-p105">Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName</span><span class="sxs-lookup"><span data-stu-id="9a42e-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="9a42e-145">Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.</span><span class="sxs-lookup"><span data-stu-id="9a42e-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="9a42e-146">Проверка адресов</span><span class="sxs-lookup"><span data-stu-id="9a42e-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="9a42e-147">Проверка адресов, хранящихся в базе данных местонахождения</span><span class="sxs-lookup"><span data-stu-id="9a42e-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="9a42e-148">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9a42e-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9a42e-149">Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="9a42e-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="9a42e-150">Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="9a42e-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="9a42e-151">Кроме того, для проверки отдельных адресов вы можете использовать командлет **Test-CsLisCivicAddress**.</span><span class="sxs-lookup"><span data-stu-id="9a42e-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="9a42e-152">Публикация базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="9a42e-152">Publish the location database</span></span>

<span data-ttu-id="9a42e-153">Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.</span><span class="sxs-lookup"><span data-stu-id="9a42e-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="9a42e-154">Если вы используете шлюзы ELIN, необходимо также загрузить номера ELIN в базу данных автоматического определения расположения (ALI) сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9a42e-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="9a42e-155">Оператор ТСОП может потребовать использования определенного формата для записей ELIN.</span><span class="sxs-lookup"><span data-stu-id="9a42e-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="9a42e-156">Обратитесь к оператору ТСОП для получения более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="9a42e-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="9a42e-157">Вы можете экспортировать записи из базы данных службы сведений о расположении и отформатировать их в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="9a42e-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="9a42e-158">Публикация базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="9a42e-158">To publish the location database</span></span>

-  <span data-ttu-id="9a42e-159">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9a42e-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="9a42e-160">Чтобы опубликовать базу данных местоположений, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="9a42e-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


