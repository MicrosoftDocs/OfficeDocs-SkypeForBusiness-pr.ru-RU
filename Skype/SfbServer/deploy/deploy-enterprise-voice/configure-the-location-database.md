---
title: Настройка базы данных местоположений в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Настройка, заполнения и опубликовать базу данных местоположений E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: f07eafbbbfcbb62c7176e35faba48e0d1281ce39
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568333"
---
# <a name="configure-the-location-database-in-skype-for-business-server-2015"></a><span data-ttu-id="d8ab7-103">Настройка базы данных местоположений в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d8ab7-103">Configure the location database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d8ab7-104">Настройка, заполнения и опубликовать базу данных местоположений E9-1-1 в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d8ab7-105">Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="d8ab7-106">Чтобы настроить базу данных местоположений, выполните следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d8ab7-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="d8ab7-107">Заполните базу данных с сопоставлением сетевых элементов местоположениям.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="d8ab7-108">Если вы используете шлюз аварийного расположение идентификационный номер (ELIN), необходимо включить ELIN в \<CompanyName\> поля.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="d8ab7-109">Если вы не заполняете базу данных расположений, и для параметра **Требуется местоположение** в политике местоположений задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="d8ab7-110">Проверка руководству Поверьте адрес по (MSAG), которое поддерживается поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="d8ab7-111">Опубликуйте обновленную базу данных.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="d8ab7-112">Наполнение базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="d8ab7-112">Populate the location database</span></span>

<span data-ttu-id="d8ab7-113">Автоматически обнаруживать клиентов в сети, необходимо сначала для заполнения базы данных местоположений географических соответствий, которая соответствует населения сетевых элементов (то есть, почтовые) адреса.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="d8ab7-114">Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="d8ab7-115">Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="d8ab7-p103">Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="d8ab7-118">**Элемент сети**</span><span class="sxs-lookup"><span data-stu-id="d8ab7-118">**Network Element**</span></span>|<span data-ttu-id="d8ab7-119">**Обязательные столбцы**</span><span class="sxs-lookup"><span data-stu-id="d8ab7-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8ab7-120">**Точка беспроводного доступа**</span><span class="sxs-lookup"><span data-stu-id="d8ab7-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="d8ab7-121">\<BSSID\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="d8ab7-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="d8ab7-122">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\<страны\></span><span class="sxs-lookup"><span data-stu-id="d8ab7-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="d8ab7-123">**Подсеть**</span><span class="sxs-lookup"><span data-stu-id="d8ab7-123">**Subnet**</span></span> <br/> |<span data-ttu-id="d8ab7-124">\<Подсети\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="d8ab7-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="d8ab7-125">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\<страны\></span><span class="sxs-lookup"><span data-stu-id="d8ab7-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="d8ab7-126">**Порт**</span><span class="sxs-lookup"><span data-stu-id="d8ab7-126">**Port**</span></span> <br/> |<span data-ttu-id="d8ab7-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="d8ab7-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="d8ab7-128">... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\< Страна\></span><span class="sxs-lookup"><span data-stu-id="d8ab7-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="d8ab7-129">**Коммутатор**</span><span class="sxs-lookup"><span data-stu-id="d8ab7-129">**Switch**</span></span> <br/> |<span data-ttu-id="d8ab7-130">\<ChassisID\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="d8ab7-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="d8ab7-131">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\<страны\></span><span class="sxs-lookup"><span data-stu-id="d8ab7-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="d8ab7-132">Добавление элементов сети в базу данных расположений</span><span class="sxs-lookup"><span data-stu-id="d8ab7-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="d8ab7-133">Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="d8ab7-p104">Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:</span><span class="sxs-lookup"><span data-stu-id="d8ab7-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="d8ab7-137">Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="d8ab7-138">Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="d8ab7-139">Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="d8ab7-140">Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="d8ab7-141">Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="d8ab7-142">Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="d8ab7-p105">Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName</span><span class="sxs-lookup"><span data-stu-id="d8ab7-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="d8ab7-145">Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="d8ab7-146">Проверка адресов</span><span class="sxs-lookup"><span data-stu-id="d8ab7-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="d8ab7-147">Проверка адресов, хранящихся в базе данных местонахождения</span><span class="sxs-lookup"><span data-stu-id="d8ab7-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="d8ab7-148">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d8ab7-149">Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="d8ab7-150">Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="d8ab7-151">Кроме того, для проверки отдельных адресов можно использовать командлет **Test-CsLisCivicAddress** .</span><span class="sxs-lookup"><span data-stu-id="d8ab7-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="d8ab7-152">Публикация базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="d8ab7-152">Publish the location database</span></span>

<span data-ttu-id="d8ab7-153">Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="d8ab7-154">Если вы используете шлюзы ELIN, необходимо также загрузить номера ELIN в базу данных автоматического определения расположения (ALI) сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="d8ab7-155">Оператор ТСОП может потребовать использования определенного формата для записей ELIN.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="d8ab7-156">Обратитесь к оператору ТСОП для получения более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="d8ab7-157">Можно экспортировать записи из базы данных службы сведения о расположении и форматировать их в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="d8ab7-158">Публикация базы данных местоположений</span><span class="sxs-lookup"><span data-stu-id="d8ab7-158">To publish the location database</span></span>

-  <span data-ttu-id="d8ab7-159">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="d8ab7-160">Чтобы опубликовать базу данных местоположений, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="d8ab7-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


