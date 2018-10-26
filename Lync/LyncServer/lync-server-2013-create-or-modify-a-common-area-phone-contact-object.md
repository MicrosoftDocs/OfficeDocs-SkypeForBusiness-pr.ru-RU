﻿---
title: Создание или изменение объекта контактов телефона общего пользования
TOCTitle: Создание или изменение объекта контактов телефона общего пользования
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ994083(v=OCS.15)
ms:contentKeyID: 52058486
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение объекта контактов телефона общего пользования

 

_**Дата изменения раздела:** 2013-02-20_

Чтобы создать объекты контактов Доменные службы Active Directory для применения со всеми телефонами общего доступа, используйте командлет **New-CsCommonAreaPhone**. Этот командлет может либо создать новые объекты контактов для использования с телефонами общего доступа, либо может связать существующие объекты контактов с новым телефоном общего доступа. Чтобы изменить свойства объектов контактов, связанные с телефонами общего доступа, используйте командлет **Set-CsCommonAreaPhone**. Дополнительные параметры для **Set-CsCommonAreaPhone** позволяют изменить элементы, такие как отображаемое имя Active Directory контакта или универсальный код ресурса (URI) линии, связанный с телефоном, а также включить или отключить учетную запись для использования с Lync Server. Подробные сведения обо всех доступных вариантах настройки см. в разделе "Параметры" в статье [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone). Дополнительные сведения о параметрах **New-CsCommonAreaPhone** см. в разделе [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone).

Эти два командлета можно выполнить из командная консоль Lync Server 2013 или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Создание объектов контактов для телефона общего доступа

  - Чтобы создать новый объект контактов для телефона общего доступа, используйте командлет **New-CsCommonAreaPhone**. Во время создания объектов контактов требуется предоставить минимум следующие сведения.
    
      - **LineUri**: телефонный номер, связанный с телефоном общего доступа. Обратите внимание, что при указании номера телефона необходимо использовать формат E.164.
    
      - **RegistrarPool**: полное доменное имя (FQDN) пула регистратора, где будет размещаться объект контактов.
    
      - **OU**: различаемое имя контейнера Active Directory, где будет создан объект контактов.
    
    Мы также рекомендуем предоставить отображаемое имя Доменные службы Active Directory. В противном случае необходимо будет использовать GUID для задания идентификатора телефона. Пример:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

## Изменение объекта контактов для телефона общего доступа

  - Чтобы изменить свойства объекта контактов существующего телефона общего доступа, используйте командлет **Set-CsCommonAreaPhone**. Например, эта команда настраивает адрес SIP для телефона общего доступа с параметром DisplayName, имеющим значение Lobby:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

Дополнительные сведения см. в разделах справки для командлетов [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone) и [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone).

