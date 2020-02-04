---
title: 'Lync Server 2013: поддержка доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Поддержка доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-07_

Lync Server 2013 использует центральное хранилище для хранения данных конфигурации для серверов и служб, вместо того чтобы полагаться на доменные службы Active Directory для этих данных, как в прошлом. Lync Server 2013 по-прежнему хранит указанные ниже в службах AD DS.

  - **Расширения схемы**
    
      - Расширения объекта пользователя
    
      - Расширения классов для Lync Server 2010 и Office Communications Server 2007 R2 для обеспечения обратной совместимости с предыдущими поддерживаемыми версиями

  - **Данные** (хранящиеся в расширенной схеме Lync Server 2013 и в существующих классах)
    
      - URI SIP пользователя и другие пользовательские параметры
    
      - Объекты контактов для приложений (например, приложение группы ответа и приложение для конференц-связи);
    
      - Данные, опубликованные для обеспечения обратной совместимости
    
      - Точка управления службой для центрального хранилища управления
    
      - Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)

В этом разделе описаны требования поддержки AD DS для Lync Server 2013. Дополнительные сведения о поддержке топологии: [Поддерживаемые топологии Active Directory в Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) в документации по поддержке.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Поддерживаемые операционные системы контроллера домена

Lync Server 2013 поддерживает контроллеры домена под управлением следующих операционных систем:

  - Операционная система Windows Server 2012 R2

  - Операционная система Windows Server 2012

  - Операционная система Windows Server 2008 R2

  - Операционная система Windows Server 2008

  - Windows Server 2008 Enterprise 32-bit

  - Версия операционной системы Windows Server 2003 R2 (32-разрядная или 64-разрядная)

  - 32-разрядная или 64-разрядная версии операционной системы Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Функциональный уровень леса и домена

Вы должны вызвать все домены, в которых развертывается сервер Lync Server 2013, на функциональном уровне домена Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или хотя бы Windows Server 2003 или более поздней версии.

Все леса, в которых развертывается Lync Server 2013, должны порождаться на функциональный уровень леса Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или не ниже Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Поддержка контроллеров домена, предназначенных только для чтения

Lync Server 2013 поддерживает развертывание доменных служб Active Directory, включающее контроллеры домена только для чтения или серверы глобального каталога только для чтения, если доступны контроллеры домена с возможностью записи.

</div>

<div>

## <a name="domain-names"></a>Доменные имена

Lync Server не поддерживает домены с одной меткой. Например, лес с корневым доменом с именем **contoso. local** поддерживается, но корневой домен с именем **Local** не поддерживается. Подробные сведения о том, как настроить Windows для доменов с DNS-именами, сопоставленными с одной меткой, можно найти в статье [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)300684 в Microsoft Knowledge Base.

<div>


> [!NOTE]  
> Lync Server не поддерживает переименование доменов. Если необходимо переименовать домен, на котором развернут сервер Lync Server, сначала необходимо удалить Lync Server, затем переименовать домен, а затем повторно установить Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Заблокированные среды AD DS

В заблокированной среде доменных служб Active Directory пользователи и объекты компьютеров часто размещаются в определенных организационных подразделениях (OU) с отключенным наследованием разрешений для обеспечения безопасности административного делегирования и включения использования объектов групповой политики (GPO) для принудительного применения политики безопасности. Lync Server 2013 можно развертывать в заблокированной среде Active Directory. Сведения о том, что необходимо для развертывания Lync Server в заблокированной среде, приведены в разделе [Подготовка заблокированных доменных служб Active Directory в Lync server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) в документации по развертыванию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

