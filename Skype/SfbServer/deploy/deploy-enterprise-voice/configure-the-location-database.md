---
title: Настройка базы данных местоположений в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Настройка, заполнения и опубликовать базу данных местоположений E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: e57f9ba299abad613df2f4c54ae9ecbbea748f9a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885501"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Настройка базы данных местоположений в Скайп для Business Server
 
Настройка, заполнения и опубликовать базу данных местоположений E9-1-1 в Скайп Business Server корпоративной голосовой связи. 
  
Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. 
  
Чтобы настроить базу данных местоположений, следует выполнить следующие задачи.
  
- Заполните базу данных с сопоставлением сетевых элементов местоположениям. Если вы используете шлюз аварийного расположение идентификационный номер (ELIN), необходимо включить ELIN в \<CompanyName\> поля.
    
    Если вы не заполняете базу данных расположений, и для параметра **Требуется местоположение** в политике местоположений задано значение **Да** или **Заявление об отказе**, клиент будет предлагать пользователю ввести расположение вручную.
    
- Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.
    
- Опубликуйте обновленную базу данных.
    
## <a name="populate-the-location-database"></a>Наполнение базы данных местоположений

Чтобы автоматически определять расположение клиентов в сети, сначала требуется заполнить базу данных местоположений в карте географических соответствий, которая сопоставляет элементы сети с городскими адресами (например, улицей). Для определения карты географических соответствий вы можете использовать подсети, точки беспроводного доступа, коммутаторы и порты.
  
Вы можете добавлять адреса в базу данных местоположений по отдельности или набором с помощью CSV-файла, который содержит форматы столбцов, описанные в следующей таблице.
  
Если вы используете шлюз экстренного идентификационного номера местоположения (Emergency Location Identification Number — ELIN), включите ELIN в поле **CompanyName** для каждого расположения. Для каждого из расположений вы можете включить несколько номеров ELIN, разделяя их точкой с запятой.
  
|**Элемент сети**|**Обязательные столбцы**|
|:-----|:-----|
|**Точка беспроводного доступа** <br/> |\<BSSID\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\<страны\>  <br/> |
|**Подсеть** <br/> |\<Подсети\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\<страны\>  <br/> |
|**Порт** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...  <br/> ... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\< Страна\>  <br/> |
|**Коммутатор** <br/> |\<ChassisID\>,\<описание\>,\<расположение\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Город\>,\<состояние\>,\<PostalCode\>,\<страны\>  <br/> |
   
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

   Кроме того, для проверки отдельных адресов можно использовать командлет **Test-CsLisCivicAddress** .
    
## <a name="publish-the-location-database"></a>Публикация базы данных местоположений

Новые расположения, добавленные вами в базу данных местоположений, останутся недоступны клиенту, пока не будут опубликованы.
  
Если вы используете шлюзы ELIN, необходимо также загрузить номера ELIN в базу данных автоматического определения расположения (ALI) сети ТСОП. Оператор ТСОП может потребовать использования определенного формата для записей ELIN. Обратитесь к оператору ТСОП для получения более подробных сведений. Можно экспортировать записи из базы данных службы сведения о расположении и форматировать их в соответствии с требованиями.
  
### <a name="to-publish-the-location-database"></a>Публикация базы данных местоположений

-  Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
- Чтобы опубликовать базу данных местоположений, выполните следующий командлет.
    
  ```
  Publish-CsLisConfiguration
  ```


