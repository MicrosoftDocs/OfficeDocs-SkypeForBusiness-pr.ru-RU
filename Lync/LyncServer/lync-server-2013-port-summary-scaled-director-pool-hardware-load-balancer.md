﻿---
title: "Lync Server 2013: обзор портов — масшт. пул директоров, аппар. балансировщик"
TOCTitle: Сводка по портам — vасштабируемый пул директоров, аппаратный балансировщик нагрузки
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204983(v=OCS.15)
ms:contentKeyID: 49310091
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сводка по портам — vасштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Требования к портам брандмауэра для единственного сервера с ролью Директоров заключаются в портах, которые используются для установки соединения с Директор из внутреннего интерфейса сервер или внутреннего интерфейса обратного прокси-сервера. Microsoft Lync Server 2013 по умолчанию ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 будут открыты от обратного прокси-сервера до сервера Директор, а также до пула серверов переднего плана (пула переднего плана) и серверов переднего плана. Кроме того, должна быть передача данных по протоколу SIP от внутреннего интерфейса пограничного сервера сервер серверу Директор, а также пулу серверов переднего плана и серверам переднего плана. Протокол SIP использует SIP/MTLS/TCP 5061 от пограничного сервера сервер к пулу серверов переднего плана и серверам переднего плана. Также должно быть создано правило, которое разрешает передачу данных SIP/MTLS/TCP 5061 от сервера Директор, пула серверов переднего плана и серверов переднего плана внутреннему интерфейсу пограничного сервера сервер.

### Порты и протоколы Директора для определений брандмауэра

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Роль/протокол/TCP или UDP/порт</th>
<th>IP-адрес источника</th>
<th>IP-адрес назначения</th>
<th>Примечания.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Виртуальный IP-адрес аппаратного балансировщика нагрузки Директор</p></td>
<td><p>Изначально получаемая внешней стороной обратного прокси-сервера, передача данных отправляется на виртуальный IP-адрес аппаратного балансировщика нагрузки Директор и в веб-службы переднего плана.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Внутренний интерфейс обратного прокси-сервера</p></td>
<td><p>Виртуальный IP-адрес аппаратного балансировщика нагрузки Директор</p></td>
<td><p>Изначально получаемая внешней стороной обратного прокси-сервера, передача данных отправляется на виртуальный IP-адрес аппаратного балансировщика нагрузки Директор и в веб-службы переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Директор</p></td>
<td><p>переднего плана или переднего плана</p></td>
<td><p>Межсерверная передача данных между виртуальным IP-адресом аппаратного балансировщика нагрузки Директор и переднего плана.</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>Виртуальный IP-адрес аппаратного балансировщика нагрузки Директор</p></td>
<td><p>Директор предоставляет веб-службы для внутренних и внешних клиентов.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Внутренние клиенты</p></td>
<td><p>Виртуальный IP-адрес аппаратного балансировщика нагрузки Директор</p></td>
<td><p>Директор предоставляет веб-службы для внутренних и внешних клиентов.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Внутренний интерфейс сервер</p></td>
<td><p>Виртуальный IP-адрес аппаратного балансировщика нагрузки Директор</p></td>
<td><p>Передача данных по протоколу SIP от сервер в Директор, а также на переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Любая</p></td>
<td><p>Директор</p></td>
<td><p>Команды и сбор данных для журналов контроллера (ClsController.exe) или агента (ClsAgent.exe) централизованная служба ведения журнала</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Любая</p></td>
<td><p>Директор</p></td>
<td><p>Команды и сбор данных для журналов контроллера (ClsController.exe) или агента (ClsAgent.exe) централизованная служба ведения журнала</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Любая</p></td>
<td><p>Директор</p></td>
<td><p>Команды и сбор данных для журналов контроллера (ClsController.exe) или агента (ClsAgent.exe) централизованная служба ведения журнала</p></td>
</tr>
</tbody>
</table>

