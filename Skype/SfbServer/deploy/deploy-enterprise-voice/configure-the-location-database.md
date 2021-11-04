---
title: Настройка базы данных расположения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Настройка, заполнение и публикация базы данных расположения E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 759dffbaf5f9370b2604534e2868cdd87933d1ef
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748915"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Настройка базы данных расположения в Skype для бизнеса Server
 
Настройка, заполнение и публикация базы данных расположения E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь. 
  
Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. 
  
Чтобы настроить базу данных расположения, выполните следующие задачи:
  
- Заполните базу данных с сопоставлением сетевых элементов местоположениям. При использовании шлюза идентификации аварийного местоположения (ELIN) необходимо включить ELIN в \<CompanyName\> поле.
    
    Если вы не заполняете базу данных расположений, и для параметра **Location Required** (Требуется расположение) в политике расположения задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.
    
- Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.
    
- Опубликуйте обновленную базу данных.
    
## <a name="populate-the-location-database"></a>Заполнение базы данных расположения

Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в карте географических соответствий, которая сопоставляет элементы сети с городскими адресами (например, улицей). Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.
  
Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.
  
Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.
  
|**Элемент сети**|**Обязательные столбцы**|
|:-----|:-----|
|**Точка беспроводного доступа** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Переключатель** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Добавление элементов сети в базу данных расположений

1. Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName
    
   Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Проверка адресов

### <a name="to-validate-addresses-located-in-the-location-database"></a>Проверка адресов, хранящихся в базе данных местонахождения

1.  Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Кроме того, для проверки отдельных адресов вы можете использовать командлет **Test-CsLisCivicAddress**.
    
## <a name="publish-the-location-database"></a>Публикация базы данных расположения

Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.
  
Если вы используете шлюзы Emergency Location Identification Number (ELIN), необходимо также загрузить номера ELIN в базу данных Automatic Location Identification (ALI) сети PSTN. Оператор PSTN может потребовать использования определенного формата для записей ELIN. Обратитесь к оператору PSTN для получения более подробных сведений. Вы можете экспортировать записи из базы данных службы сведений о расположении и форматировать их по мере необходимости.
  
### <a name="to-publish-the-location-database"></a>Публикация базы данных местоположений

-  Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
- Чтобы опубликовать базу данных местоположений, выполните следующий командлет.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


