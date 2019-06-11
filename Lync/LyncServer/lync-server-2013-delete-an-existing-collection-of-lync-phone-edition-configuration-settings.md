---
title: Удаление существующей коллекции параметров конфигурации Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Если вы больше не хотите использовать коллекцию параметров для устройств с Lync Phone Edition, удалите ее. Если вы удалите коллекцию для сайта, глобальные параметры будут применены к телефонам на этом сайте. Вы не можете удалить глобальную коллекцию.

<div>


> [!NOTE]
> Вместо удаления коллекции, возможно, потребуется изменить некоторые параметры. Подробнее о том, как это сделать, можно найти <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">в разделе Создание или изменение семейства параметров конфигурации Lync Phone Edition в Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Удаление коллекции параметров конфигурации Lync Phone Edition

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации устройства** .

4.  На странице **Конфигурация устройства** выберите коллекцию, которую вы хотите удалить, а затем в меню **Правка** выберите команду **Удалить**.
    
    <div>
    

    > [!NOTE]
    > Если вы удалите глобальную коллекцию, для параметров будет восстановлены параметры по умолчанию. Коллекция не выходит за края.

    
    </div>

5.  В диалоговом окне подтверждения нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell

Вы можете удалить параметры конфигурации Lync Phone Edition с помощью Windows PowerShell и командлета **Remove-ксукконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Удаление заданной коллекции параметров конфигурации Lync Phone Edition

  - Эта команда удаляет параметры конфигурации телефона UC, примененные к сайту Redmond.
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации Lync Phone Edition, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации телефона UC, примененные к области действия службы.
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Удаление всех параметров конфигурации Lync Phone Edition с отключенной блокировкой телефона

  - Эта команда удаляет все наборы параметров конфигурации телефона UC, в которых заблокирована телефонная блокировка.
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Подробности можно найти в разделе [Remove-ксукфонеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

