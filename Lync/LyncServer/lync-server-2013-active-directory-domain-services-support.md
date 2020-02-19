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
ms.openlocfilehash: b200fb122f436e7afa5587e56a9e62edd0d3fa5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Поддержка доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

Lync Server 2013 использует центральное хранилище управления для хранения данных конфигурации для серверов и служб, вместо того чтобы полагаться на доменные службы Active Directory для этих данных, как в предыдущих версиях. Lync Server 2013 по-прежнему сохраняет следующее в AD DS:

  - **Расширения схемы**
    
      - Расширения объекта пользователя
    
      - Расширения для классов Lync Server 2010 и Office Communications Server 2007 R2 для обеспечения обратной совместимости с предыдущими поддерживаемыми версиями

  - **Данные** (хранящиеся в расширенной схеме Lync Server 2013 и в существующих классах)
    
      - URI SIP пользователя и другие пользовательские параметры
    
      - Объекты Contact для приложений (например, приложение группы ответа и приложение для конференц-связи)
    
      - Данные, опубликованные для обеспечения обратной совместимости
    
      - Точка управления службой (SCP) для центрального хранилища управления
    
      - Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)

В этом разделе описываются требования к поддержке доменных служб Active Directory для Lync Server 2013. Подробные сведения о поддержке топологии приведены [в статье поддерживаемые топологии Active Directory в Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) в документации по поддержке.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Поддерживаемые ОС контроллера домена

Lync Server 2013 поддерживает контроллеры домена под управлением следующих операционных систем:

  - Операционная система Windows Server 2012 R2

  - Операционная система Windows Server 2012

  - Операционная система Windows Server 2008 R2

  - Операционная система Windows Server 2008

  - Windows Server 2008 Enterprise 32 — bit

  - 32- и 64-разрядные версии ОС Windows Server 2003 R2

  - 32 или 64 – разрядная версия операционной системы Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Режим работы леса и домена

Необходимо вызвать все домены, в которых выполняется развертывание Lync Server 2013, на функциональном уровне домена Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или хотя бы Windows Server 2003 или более поздней версии.

Все леса, в которых развертывается Lync Server 2013, должны вызываться в режиме работы леса Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 или по крайней мере Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Поддержка контроллеров домена только для чтения

Lync Server 2013 поддерживает развертывания доменных служб Active Directory, которые включают контроллеры домена только для чтения или серверы глобального каталога только для чтения, если имеются доступные контроллеры домена с возможностью записи.

</div>

<div>

## <a name="domain-names"></a>Имена доменов

Lync Server не поддерживает домены с одной меткой. Например, лес с корневым доменом **contoso.local** будет поддерживаться, а с корневым доменом **local** — нет. Дополнительные сведения см. в статье 300684 базы знаний Майкрософт "сведения о настройке Windows для доменов с DNS-именем, сопоставленными с [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752)одной меткой" по адресу ".

<div>


> [!NOTE]  
> Lync Server не поддерживает переименование доменов. Если требуется переименовать домен, на котором развернут Lync Server, сначала необходимо удалить Lync Server, затем переименовать домен, а затем переустановить Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Заблокированные среды доменных служб Active Directory

В заблокированной среде доменных служб Active Directory объекты "Пользователи и компьютер" часто размещаются в особых подразделениях с отключенным наследованием разрешений в целях обеспечения безопасного делегирования административных полномочий и включения использования объектов групповой политики (GPO) для применения политик безопасности. Lync Server 2013 можно развернуть в заблокированной среде Active Directory. Дополнительные сведения о том, что необходимо для развертывания Lync Server в заблокированной среде, приведено в статье [Подготовка заблокированных доменных служб Active Directory в Lync server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) в документации по развертыванию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

