---
title: 'Lync Server 2013: классы и описания схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a7da8bf5781de56f89e19359168530597ef977
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Классы и описания схемы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-30_

В этом разделе описываются все классы схемы, используемые в Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Классы схемы и описания


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Класс</th>
<th>Описание</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Получатель электронной почты единой системы обмена сообщениями Exchange.</p></td>
<td><p>Этот вспомогательный класс предоставляется совместно с единой системой обмена сообщениями Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Аппликатионконтактс</p></td>
<td><p>Этот класс является контейнером для нескольких контактов приложения и не содержит никакие атрибуты.</p></td>
<td><p>Новые данные в Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — ApplicationServer</p></td>
<td><p>Этот класс размещает запись точки управления службой для экземпляра служб Unified Communications Application Services (UCAS).</p></td>
<td><p>Новое в Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Аппликатионсерверсервице</p></td>
<td><p>Этот класс предоставляет связь из определенного пула со службой приложения.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Аппликатионсерверсеттингс</p></td>
<td><p>Этот вспомогательный класс в msRTCSIP – ApplicationServer содержит атрибуты, представляющие параметры для экземпляров службы приложения.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (устаревший)</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к архивации.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (устаревший)</p></td>
<td><p>Этот класс представляет один сервер архивации обмена мгновенными сообщениями. Экземпляр этого класса создается при активации компьютера в качестве сервера архивации обмена мгновенными сообщениями, например, компьютера с установленной службой архивации обмена мгновенными сообщениями.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — ConferenceDirectories</p></td>
<td><p>Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит никакие атрибуты.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Конференцедиректори</p></td>
<td><p>Этот класс содержит атрибуты, представляющие параметры для конкретного каталога конференций.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Коннектионпоинт</p></td>
<td><p>Общая точка управления службой (SCP) для указания компьютера в качестве сервера, на котором работает Lync Server.</p></td>
<td><p>Новые в Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Дефаултквабанк</p></td>
<td><p>Этот вспомогательный класс содержит параметры банка Microsoft Lync Web App.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — domain</p></td>
<td><p>Этот класс содержит атрибуты, задающие настроенные домены регистратора SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Еджепрокси</p></td>
<td><p>Этот контейнер класса представляет одну службу пограничного доступа. Так как служба пограничного доступа разворачивается в сети периметра, а клиенты обычно не разрешают доменным службам Active Directory доступ из сети периметра, экземпляры пограничной службы доступа не присоединяются к сети Active Directory интрасети. Следовательно, прокси-серверы доступа не регистрируются в AD DS автоматически. Администратор должен вручную настроить существование каждого экземпляра службы пограничного доступа в AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Ентерприсемкусеттингс</p></td>
<td><p>Этот дополнительный к msRTCSIP-MCU класс содержит атрибуты, представляющие параметры для серверов конференций.</p></td>
<td><p>Новые данные в Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Ентерприсемедиатионсерверсеттингс</p></td>
<td><p>Этот дополнительный к msRTCSIP-MediationServer класс содержит атрибуты, представляющие параметры для серверов-посредников.</p></td>
<td><p>Новые в Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Ентерприсесерверсеттингс</p></td>
<td><p>Этот дополнительный к msRTCSIP-Server класс содержит атрибуты, представляющие параметры для серверов SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Федерация</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к федерации.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Globalcontainer класс</p></td>
<td><p>В этом классе хранятся все параметры, применяемые во время развертывания Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (устаревший)</p></td>
<td><p>Этот класс представляет одну политику собраний Office Communications Server.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Глобалтопологисеттинг</p></td>
<td><p>Локальный объект параметров глобальной топологии.</p></td>
<td><p>Новые в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Глобалтопологисеттингс</p></td>
<td><p>Контейнер для хранения объектов параметров глобальной топологии.</p></td>
<td><p>Новые в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Локалнормализатион</p></td>
<td><p>Этот класс является контейнером, представляющим экземпляр правила нормализации местонахождения.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Локатионконтактмаппинг</p></td>
<td><p>Этот класс создается приложением-помощником по конференц-связи и содержит атрибуты, используемые для категоризации телефонных номеров конференций по регионам.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Локатионконтактмаппингс</p></td>
<td><p>Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местонахождений и не содержит никакие атрибуты.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — LocationProfile</p></td>
<td><p>Этот класс является контейнером, представляющим конкретный профиль местонахождения.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (устаревший)</p></td>
<td><p>Этот класс является контейнером для нескольких профилей местонахождений и не содержит какие-либо атрибуты.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (устаревший)</p></td>
<td><p>Этот класс является контейнером для нескольких локальных правил нормализации и не содержит какие-либо атрибуты.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — MCU</p></td>
<td><p>Этот класс представляет один сервер конференций.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Мкуфакториес</p></td>
<td><p>Этот класс размещает несколько классов msRTCSIP-MCUFactory и не содержит какие-либо атрибуты.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — MCUFactory</p></td>
<td><p>Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа среды передачи. Экземпляр этого класса создается, когда активируется первый сервер конференций для этого конкретного типа.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Мкуфакторисервице</p></td>
<td><p>Этот класс предоставляет связь конкретного пула с его фабрикой серверов конференций.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — MediationServer</p></td>
<td><p>В этом классе содержится запись точки управления службой для сервера-посредника.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (устаревший)</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие настраиваемые параметры собрания.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — мобильность</p></td>
<td><p>Контейнер, хранящий глобальные параметры мобильности.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Мониторингсервер</p></td>
<td><p>Этот класс содержит атрибуты, представляющие параметры для одного сервера мониторинга.</p></td>
<td><p>Новый сервер Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (устаревший)</p></td>
<td><p>Этот класс является контейнером, представляющим экземпляр наименее затратного маршрута к шлюзу или ряду шлюзов. Данная информация используется всеми пулами или серверами Enterprise, на которых установлен выпуск Standard Edition, для маршрутизации исходящих вызовов в телефонную сеть общего пользования (ТСОП) по принципу наименьшей стоимости.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (устаревший)</p></td>
<td><p>Этот класс является контейнером для нескольких наименее затратных маршрутов и не содержит какие-либо атрибуты.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (устаревший)</p></td>
<td><p>Этот класс содержит несколько классов политики Lync Server и не имеет никаких атрибутов.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — пул</p></td>
<td><p>Этот класс представляет один пул Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — пулы</p></td>
<td><p>Этот класс содержит несколько пулов Lync Server и не содержит никакие атрибуты.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Пулсервице</p></td>
<td><p>Этот класс представляет точку управления службой пула. Атрибут msRTCSIP-PrimaryHomeServer пользователей, размещенных в пуле, указывает на экземпляр данного класса.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — присутствие</p></td>
<td><p>Контейнер, хранящий глобальные параметры присутствия.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — регистратор</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие пользовательские параметры, которые поддерживаются серверами регистратора SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (устаревший)</p></td>
<td><p>Этот класс является контейнером, представляющим экземпляр использования телефонных маршрутов. Класс использований телефонных маршрутов состоит из поля атрибута и поля описания. Поле атрибута определяет тип использования. В поле описания администраторы могут ввести описание использования для этого атрибута в телефонном маршруте.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (устаревший)</p></td>
<td><p>Этот класс содержит несколько экземпляров класса msRTCSIP-RouteUsage и не имеет никаких атрибутов.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Поиск</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, которые ограничивают область результатов поиска и управляют ею.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — сервер</p></td>
<td><p>Этот класс представляет один сервер, на котором работает Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — служба</p></td>
<td><p>Этот класс содержит контейнер глобальных параметров и объекты класса msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Трустедмку</p></td>
<td><p>Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера конференций.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Трустедмкус</p></td>
<td><p>Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedMCU и не имеет никаких атрибутов.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Трустедпроксиес</p></td>
<td><p>Этот класс содержит несколько экземпляров классов msRTCSIP-TrustedProxy и не имеет никаких атрибутов.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Трустедпрокси</p></td>
<td><p>Этот класс является контейнером, представляющим сервер, на котором работает прокси-сервер. Экземпляр данного класса создается при активации нового прокси-сервера на компьютере, подключенном к AD DS.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — TrustedServer</p></td>
<td><p>Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Трустедсервице</p></td>
<td><p>Этот класс является контейнером, представляющим доверенную службу, которая маршрутизируется с помощью адреса GRUU. Экземпляр этого класса создается при активации нового сервера, который является доверенным для Lync Server. Этот доверенный сервер должен быть подключен к домену Active Directory.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Трустедсервицес</p></td>
<td><p>Этот класс является контейнером для нескольких серверов GRUU и не содержит никакие атрибуты.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Трустедвебкомпонентссервер</p></td>
<td><p>Этот класс содержит атрибуты, которые представляют параметры для доверенного веб-компонента.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Трустедвебкомпонентссерверс</p></td>
<td><p>Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedWebComponentServer и не имеет никаких атрибутов.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (устаревший)</p></td>
<td><p>Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, относящиеся к объединенным коммуникациям.</p></td>
<td><p>Устаревшие в Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — компоненты</p></td>
<td><p>Этот класс содержит точку управления службой для сервера IIS. Он определяет сервер как сервер веб-компонентов.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Вебкомпонентссервице</p></td>
<td><p>Этот класс предоставляет связь конкретного пула с веб-компонентом, который будет использовать этот пул.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Вебкомпонентсеттингс</p></td>
<td><p>Этот дополнительный к msRTCSIP-WebComponents класс содержит атрибуты, представляющие параметры для веб-компонентов.</p></td>
<td><p>Новый сервер Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

