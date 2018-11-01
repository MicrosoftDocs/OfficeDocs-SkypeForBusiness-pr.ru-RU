﻿---
title: Удаление существующей коллекции параметров конфигурации версий клиентов
TOCTitle: Удаление существующей коллекции параметров конфигурации версий клиентов
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ898480(v=OCS.15)
ms:contentKeyID: 52058249
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление существующей коллекции параметров конфигурации версий клиентов

 

_**Дата изменения раздела:** 2013-02-23_

Если вы хотите удалить ранее заданные для сайта параметры конфигурации клиента, это можно сделать из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

## Удаление параметров конфигурации клиента с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Clients** (Клиенты) и затем нажмите кнопку навигации **Client Version Configuration** (Конфигурация версий клиентов).

4.  Выберите сайт, щелкните элемент **Edit** (Изменить), элемент **Delete** (Удалить) и нажмите кнопку **OK** (ОК).

## Удаление параметров конфигурации версии клиента с помощью командлетов Windows PowerShell

Вы можете удалить параметры конфигурации версии клиента с помощью командлета **Remove-CsClientVersionConfiguration**. Для выполнения этого командлета может использоваться командная консоль Lync Server 2013 или удаленный сеанс Windows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Удаление указанной коллекции параметров конфигурации версии клиента

  - Следующая команда удаляет параметры конфигурации версии клиента, применяемые к сайту Redmond.
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

## Удаление всех параметров конфигурации версии клиента, примененных на уровне сайта

  - Эта команда удаляет все параметры конфигурации версии клиента, настроенные на уровне сайта:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## Удаление всех параметров конфигурации версии клиента в зависимости от значения свойства DefaultAction

  - А эта команда удаляет все параметры конфигурации версии клиента, для которых было установлено действие по умолчанию "Блокировать" (Block):
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

Дополнительные сведения см. в разделе справки по командлету [Remove-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionConfiguration).

