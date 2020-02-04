---
title: 'Lync Server 2013: контрольный список развертывания для E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efe5c55386eb431c91e798ad960cc510ce33ce1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Контрольный список развертывания для E9-1-1 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

Чтобы эффективно спланировать Улучшенный 9-1-1 (E9-1-1), включите следующие требования к развертыванию:

  - Необходимые условия для развертывания E9-1-1.

  - Шаги, необходимые для развертывания E9-1-1.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Необходимые компоненты для развертывания E9-1-1

Прежде чем развертывать E9-1-1, вы должны уже разворачивать внутренние серверы Lync Server, в том числе централизованное хранилище управления, пул переднего плана или сервер стандартных выпусков, один или несколько серверов или пулов серверов-исправлений, а также клиенты Lync Server. In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN). Lync Server поддерживает использование поставщиков услуг E9-1-1 только в США.

</div>

<div>

## <a name="deployment-process"></a>Процесс развертывания

В следующей таблице представлен обзор процесса развертывания E9-1-1. Дополнительные сведения о действиях по развертыванию можно найти в статье [Настройка улучшенных 9-1-1 в Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) в документации по развертыванию.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка использования, маршрутов и конфигурации магистрали для голосовой связи</p></td>
<td><ol>
<li><p>Создайте новую запись об использовании ТСОП. Ее имя совпадает с именем, которое используется для параметра <strong>Использование ТСОП</strong> в политике расположения.</p></li>
<li><p>Создайте или назначьте голосовой маршрут в записи использования ТСОП, созданную на предыдущем шаге, а затем укажите в атрибуте шлюза SIP-магистраль E9-1-1 или шлюз ELIN. </p></li>
<li><p>Для поставщика услуг E9-1-1 магистрали SIP установите магистраль, которая будет обрабатывать вызовы E9-1-1 в SIP для передачи данных PIDF-LO, используя командлет <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>При необходимости для поставщика услуг E9-1-1 SIP-магистрали создайте или назначьте локальный маршрут PSTN для вызовов, которые не обрабатываются SIP-магистралью поставщика услуг E9-1-1. Этот маршрут будет использоваться, если связь с поставщиком услуг E9-1-1 недоступна. Если это поддерживается поставщиком услуг E9-1-1, назначьте правило конфигурации магистрали шлюзу, который преобразует строку набора 911 в номер DID национальной или региональной экстренной службы (ECRC).</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Настройка маршрута голосовой связи E9-1-1 в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Создайте политики местоположения и назначьте их пользователям и подсетям</p></td>
<td><ol>
<li><p>Изучите глобальную политику расположения.</p></li>
<li><p>Создайте политику расположения в области на уровне пользователя; или, если в организации несколько узлов с различными способами использования экстренных вызовов, создайте политику расположения в области на уровне сети.</p></li>
<li><p>Назначьте политику расположения сетевым узлам.</p></li>
<li><p>Добавьте соответствующие подсети к сетевому узлу.</p></li>
<li><p>(Необязательно) Назначьте политику расположения политикам пользователя.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (кроме создания политик расположения)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Создание политик местоположений в Lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Добавление политики расположения на сайт сети в Lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Связывание подсетей с сетевыми сайтами для E9-1-1 в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка базы данных местоположений</p></td>
<td><ol>
<li><p>Заполните базу данных с сопоставлением сетевых элементов местоположениям.</p></li>
<li><p>Для шлюзов Елин добавьте Елинс в столбец &lt;CompanyName.&gt;</p></li>
<li><p>Настройте подключение к поставщику услуг E9-1-1 для проверки адресов.</p></li>
<li><p>Сверьте адреса у поставщика услуг E9-1-1.</p></li>
<li><p>Опубликуйте обновленную базу данных.</p></li>
<li><p>Для шлюзов ELIN загрузите ELIN в базу данных ALI вашего поставщика услуг.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Необязательно) Настройка дополнительных функций</p></td>
<td><ol>
<li><p>Настройте URL-адрес для приложения SNMP.</p></li>
<li><p>Настройте URL-адрес расположения дополнительной службы сведений о расположении.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Настройка приложения SNMP в Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Настройка дополнительной службы сведений о расположении в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

