---
title: Просмотр отчетов администратора в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Компонент "Administrator Reports" (Отчеты администратора) предоставляют подробную информацию для развертывания и проведения операций. Отчеты создаются на базе параметров, выбранных в области Design Sites (Разработка сайтов). Проектировщик может получить дополнительную выгоду от использования компонента "Administrator Reports" (Отчеты администратора), изменив схемы сети и определив полные IP-адреса и полные доменные имена для серверов, пулов и подсистем балансировки нагрузки.
ms.openlocfilehash: 5cab8231428ace2a0d77132481819eed304d3519
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898196"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

Компонент "Administrator Reports" (Отчеты администратора) предоставляют подробную информацию для развертывания и проведения операций. Отчеты создаются на базе параметров, выбранных в области **Design Sites** (Разработка сайтов). Проектировщик может получить дополнительную выгоду от использования компонента "Administrator Reports" (Отчеты администратора), изменив схемы сети и определив полные IP-адреса и полные доменные имена для серверов, пулов и подсистем балансировки нагрузки.

Функция "Administrator Reports" (Отчеты администратора) позволяет выполнять следующее:

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Просмотр сводного отчета
<a name="Summary_report"> </a>

Скайп для администратора Business отчета является первым четыре ценных отчетов, которые документов к проекту подробно. Информация, приведенная в этом и трех других отчетах, отлично подходит для использования вашими ИТ-группами:

![Общий сводный отчет для администратора](../../media/General_Summary_Report_Admin_Report.png)

Сводный отчет содержит общую информацию о конфигурации, связанную с вашей сетью периметра. Документируются следующие аспекты: расположение, полное доменное имя и IP-адрес, тип сети и компоненты, характерные для заданной роли.

Проектировщик и каждая из групп, которые будут осуществлять развертывание, обслуживание данной инфраструктуры и управление ей, должны просматривать сводный отчет для обеспечения точности и минимального количества ошибок.

Также можно просматривать более подробные отчеты:

- Отчет по сертификатам

- Отчет по брандмауэрам

- Отчет по DNS

## <a name="review-the-certificates-report"></a>Просмотр отчета по сертификатам
<a name="Certificates_Report"> </a>

Сертификаты отчет содержит все сертификаты, которые необходимы в рекомендуемые Скайп для развертывания Business Server 2015. Планирование по сокращению имена субъекта и альтернативные имена субъектов, которые были введены. Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates. Certificate information also contains information about where the certificate can typically be issued from. If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider. Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.

![Отчет по сертификатам для администратора](../../media/Certificates_Report_Admin_Report.png)

Тщательно рассмотрите и осознайте использование и назначение каждого сертификата в развертывании. Если возникает вопрос о том, для чего именно нужен определенный сертификат, определите взаимодействие серверов и служб. Сертификаты в Скайп для Business Server 2015 используются для двух основных целей:

- Взаимная Transport Layer Security (MTLS) - компьютеров, участвующих в связи представить с сертификатом, который подтверждает их подлинность на другой компьютер. Это называется проверкой подлинности сервера. Связи не может начинаться до каждый компьютер доверяет identity на другом компьютере.

- Шифрование - шифрования (Secure Sockets Layer или SSL и протокол TLS или протокол TLS) — критические средства для обеспечения безопасности связи, помочь обеспечить конфиденциальность и создание надежного системы коммуникаций и совместной работы.

## <a name="review-the-firewall-report"></a>Просмотр отчета по брандмауэрам
<a name="Firewall_report"> </a>

Скайп для Business Server 2015 имеет ряд потенциально сложные правила брандмауэра. Средство планирования уменьшает сложность, создав отчет, который определяет подробно все требования к брандмауэру, на основе критерия ввода конструктора. The IT firewall administrator will be able to use this report to configure and define the necessary rules.

При управлении брандмауэром этот отчет следует тщательно анализировать на предмет конфликтов с имеющимися правилами брандмауэра и нарушений имеющихся политик или процедур.

![Отчет по брандмауэрам для администратора](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Просмотр отчета по DNS
<a name="DNS_Report"> </a>

Отчет по DNS, который входит в состав отчета администратора, описывает все рекомендуемые и известные записи для службы доменных имен (DNS) во внутренней сети, сети периметра и внешних сетях. Если проектировщик закончил вносить правки в схему сети, а для всех IP-адресов и полных доменных имен заданы их рабочие значения, отчет по DNS предоставляет отличный ресурс конфигурации. Кроме того, данный отчет может выступать в качестве документа по диагностике в рабочих условиях.

![Отчет по DNS для администратора](../../media/DNS_Report_Admin_Report.png)

Попросите свою группу управления DNS тщательно изучить отчет по DNS, чтобы убедиться в отсутствии ошибок, которые могут вызвать проблемы при развертывании или затруднить диагностику.

## <a name="see-also"></a>См. также
<a name="DNS_Report"> </a>

[Reviewing the Administrator Reports](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
