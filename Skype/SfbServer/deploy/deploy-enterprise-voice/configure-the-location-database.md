---
title: Настройка базы данных местоположений в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Настройте, заполните и опубликуйте базу данных расположения E9-1-1 в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 36ddd57e39b51171581c0c6316f165f44879e3f9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233689"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Настройка базы данных местоположений в Skype для бизнеса Server
 
Настройте, заполните и опубликуйте базу данных расположения E9-1-1 в Skype для бизнеса Server Enterprise. 
  
Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. 
  
Чтобы настроить базу данных местоположений, следует выполнить следующие задачи.
  
- Заполните базу данных с сопоставлением сетевых элементов местоположениям. При использовании шлюза идентификационный номер места для экстренного реагирования (Елин) необходимо добавить Елин в поле \<CompanyName\> .
    
    Если вы не заполняете базу данных расположений, и для параметра **Требуется местоположение** в политике местоположений задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.
    
- Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.
    
- Опубликуйте обновленную базу данных.
    
## <a name="populate-the-location-database"></a>Наполнение базы данных местоположений

Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в карте географических соответствий, которая сопоставляет элементы сети с городскими адресами (например, улицей). Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.
  
Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.
  
Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.
  
|**Элемент сети**|**Обязательные столбцы**|
|:-----|:-----|
|**Точка беспроводного доступа** <br/> |\<BSSID\>,\<Описание\>,\<расположение\>,\<CompanyName\>,\<хаусенумбер\>,\<хаусенумберсуффикс\>,\<преднаправленный\>,...  <br/> ... \<Стритнаме\>,\<стритсуффикс\>,\<\>i Direction\<, City\>,\<штат\>,\<PostalCode\>, страна\<\>  <br/> |
|**Subnet** <br/> |\<\>Подсеть\<,\>Описание\<,\>расположение\<,\>CompanyName\<,\>хаусенумбер\<,\>хаусенумберсуффикс\<, преднаправленный\>,...  <br/> ... \<Стритнаме\>,\<стритсуффикс\>,\<\>i Direction\<, City\>,\<штат\>,\<PostalCode\>, страна\<\>  <br/> |
|**Порт** <br/> |\<Чассисид\>,\<портидсубтипе\>,\<Портид\>,\<Описание\>,\<расположение\>,\<CompanyName\>,\<хаусенумбер\>,\< Хаусенумберсуффикс\>,...  <br/> ... \<Преднаправленный\>,\<стритнаме\>,\<стритсуффикс\>,\<\>двусторонний\<, город\>,\<штат\>,\<индекс,\>\< Страну\>  <br/> |
|**Коммутатор** <br/> |\<Чассисид\>,\<Описание\>,\<расположение\>,\<CompanyName\>,\<хаусенумбер\>,\<хаусенумберсуффикс\>,\<преднаправленный\>,...  <br/> ... \<Стритнаме\>,\<стритсуффикс\>,\<\>i Direction\<, City\>,\<штат\>,\<PostalCode\>, страна\<\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Добавление элементов сети в базу данных расположений

1. Выполните следующий командлет, чтобы добавить расположение подсети в базу данных расположения.
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Для шлюзов ELIN укажите номер ELIN в поле CompanyName. Можно указать несколько номеров ELIN. Например:
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Вы также можете запустить следующие командлеты и использовать файл "subnets.csv" для массового обновления расположений подсетей.
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Выполните следующий командлет, чтобы добавить беспроводные расположения в базу данных расположений.
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Вы также можете запустить следующие командлеты и использовать файл "waps.csv" для массового обновления расположений точек беспроводного доступа.
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Выполните следующий командлет, чтобы добавить расположения коммутаторов в базу данных расположений.
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Вы также можете запустить следующие командлеты и использовать файл "switches.csv" для массового обновления расположений коммутаторов.
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Выполните следующий командлет, чтобы добавить расположения портов в базу данных расположений.
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Значение по умолчанию PortIDSubType — LocallyAssigned. Также можно задать значения InterfaceAlias или InterfaceName
    
   Вы также можете запустить следующие командлеты и использовать файл "ports.csv" для массового обновления расположений портов.
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Проверка адресов

### <a name="to-validate-addresses-located-in-the-location-database"></a>Проверка адресов, хранящихся в базе данных местонахождения

1.  Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Кроме того, для проверки отдельных адресов вы можете использовать командлет **Test-CsLisCivicAddress**.
    
## <a name="publish-the-location-database"></a>Публикация базы данных местоположений

Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.
  
Если вы используете шлюзы ELIN, необходимо также загрузить номера ELIN в базу данных автоматического определения расположения (ALI) сети ТСОП. Оператор ТСОП может потребовать использования определенного формата для записей ELIN. Обратитесь к оператору ТСОП для получения более подробных сведений. Вы можете экспортировать записи из базы данных службы сведений о расположении и отформатировать их в соответствии с требованиями.
  
### <a name="to-publish-the-location-database"></a>Публикация базы данных местоположений

-  Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
- Чтобы опубликовать базу данных местоположений, выполните следующий командлет.
    
  ```
  Publish-CsLisConfiguration
  ```


