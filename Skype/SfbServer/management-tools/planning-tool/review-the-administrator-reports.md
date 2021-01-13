---
title: Просмотр отчетов администратора в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Отчеты администратора — это подробные сведения о развертывании и операциях. Отчеты создаются на основе выборок, помеченных на сайтах разработки. Разработчик может дополнительно добавить значение в отчеты администратора, изредактив сетевые схемы и определив полные IP-адреса и полные доменные имена для серверов, пулов и балансировщиков нагрузки.
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823349"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="27d57-105">Просмотр отчетов администратора в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="27d57-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="27d57-106">Отчеты администратора — это подробные сведения о развертывании и операциях.</span><span class="sxs-lookup"><span data-stu-id="27d57-106">The Administrator Reports are detailed information for deployment and operations.</span></span> <span data-ttu-id="27d57-107">Отчеты создаются на основе выделения, отмеченного в **сайте разработки.**</span><span class="sxs-lookup"><span data-stu-id="27d57-107">The reports are generated based on the selections marked in **Design Sites**.</span></span> <span data-ttu-id="27d57-108">Разработчик может дополнительно добавить значение в отчеты администратора, изредактив сетевые схемы и определив полные IP-адреса и полные доменные имена для серверов, пулов и балансировщиков нагрузки.</span><span class="sxs-lookup"><span data-stu-id="27d57-108">The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="27d57-109">Функция отчетов администратора позволяет:</span><span class="sxs-lookup"><span data-stu-id="27d57-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="27d57-110">Просмотр сводного отчета</span><span class="sxs-lookup"><span data-stu-id="27d57-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="27d57-111">Просмотр отчета по сертификатам</span><span class="sxs-lookup"><span data-stu-id="27d57-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="27d57-112">Просмотр отчета по брандмауэру</span><span class="sxs-lookup"><span data-stu-id="27d57-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="27d57-113">Просмотр отчета DNS</span><span class="sxs-lookup"><span data-stu-id="27d57-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="27d57-114">Просмотр сводного отчета</span><span class="sxs-lookup"><span data-stu-id="27d57-114">Review the Summary Report</span></span>
<span data-ttu-id="27d57-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="27d57-115"><a name="Summary_report"> </a></span></span>

<span data-ttu-id="27d57-116">Отчет администратора Skype для бизнеса — это первый из четырех важных отчетов, подробно документировать проект.</span><span class="sxs-lookup"><span data-stu-id="27d57-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="27d57-117">Сведения в этом отчете и трех других связанных отчетах полезны для вашей ИТ-команды:</span><span class="sxs-lookup"><span data-stu-id="27d57-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![Общий сводный отчет администратора](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="27d57-119">Сводный отчет содержит общие сведения о конфигурации, связанные с вашей сетью Edge.</span><span class="sxs-lookup"><span data-stu-id="27d57-119">The Summary Report lists general configuration information associated with your Edge network.</span></span> <span data-ttu-id="27d57-120">Задокументировано расположение, полное доменное имя и IP-адрес, тип сети и комментарии для определенной роли.</span><span class="sxs-lookup"><span data-stu-id="27d57-120">The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="27d57-121">Конструктор и каждая из команд, которые будут развертывать инфраструктуру, управлять и обслуживать ее, должны просмотреть сводный отчет на точность и убедиться в том, что ошибки находятся как минимум на уровне.</span><span class="sxs-lookup"><span data-stu-id="27d57-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="27d57-122">Вы также можете просмотреть более подробные отчеты:</span><span class="sxs-lookup"><span data-stu-id="27d57-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="27d57-123">Отчет по сертификатам</span><span class="sxs-lookup"><span data-stu-id="27d57-123">Certificates Report</span></span>

- <span data-ttu-id="27d57-124">Отчет по брандмауэру</span><span class="sxs-lookup"><span data-stu-id="27d57-124">Firewall Report</span></span>

- <span data-ttu-id="27d57-125">Отчет по DNS</span><span class="sxs-lookup"><span data-stu-id="27d57-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="27d57-126">Просмотр отчета по сертификатам</span><span class="sxs-lookup"><span data-stu-id="27d57-126">Review the Certificates Report</span></span>
<span data-ttu-id="27d57-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="27d57-127"><a name="Certificates_Report"> </a></span></span>

<span data-ttu-id="27d57-128">Отчет по сертификатам содержит все сертификаты, необходимые в рекомендуемом развертывании Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="27d57-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="27d57-129">В средстве планирования ввели имена субъектов и альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="27d57-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="27d57-130">Текст по умолчанию, который остается неустановленным, может представлять потенциальную проблему для команды, ответственной за запрос и выдачу сертификатов.</span><span class="sxs-lookup"><span data-stu-id="27d57-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="27d57-131">Сведения о сертификате также содержат сведения о том, откуда обычно может быть выдан сертификат.</span><span class="sxs-lookup"><span data-stu-id="27d57-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="27d57-132">Если инфраструктура не имеет внутренней инфраструктуры открытых ключей (PKI), все сертификаты можно запросить у поставщика общедоступных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="27d57-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="27d57-133">Расширенные области использования ключей (EKU) и поля "Назначить" в отчете очень полезны для понимания назначения и расположения каждого сертификата.</span><span class="sxs-lookup"><span data-stu-id="27d57-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![Отчет об администрировании сертификатов](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="27d57-135">Внимательно просмотрите и убедитесь, что понимается использование и назначение каждого сертификата в развертывании.</span><span class="sxs-lookup"><span data-stu-id="27d57-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="27d57-136">Если возникает вопрос о том, что делает сертификат, определите, к каков серверу или службе.</span><span class="sxs-lookup"><span data-stu-id="27d57-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="27d57-137">Сертификаты в Skype для бизнеса Server 2015 используются для двух основных целей:</span><span class="sxs-lookup"><span data-stu-id="27d57-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="27d57-138">MtLS — компьютеры, участвующие в связи, представляют сертификат, который подтверждает их личность на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="27d57-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="27d57-139">Это называется проверкой подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="27d57-139">This is known as server authentication.</span></span> <span data-ttu-id="27d57-140">Связь не может начинаться, пока каждый компьютер не доверяет удостоверению другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="27d57-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="27d57-141">Шифрование — шифрование (протокол SSL, протокол TLS или протокол TLS) является критически важным средством обеспечения безопасности коммуникаций, обеспечения конфиденциальности и создания надежной системы взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="27d57-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="27d57-142">Просмотр отчета по брандмауэру</span><span class="sxs-lookup"><span data-stu-id="27d57-142">Review the Firewall Report</span></span>
<span data-ttu-id="27d57-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="27d57-143"><a name="Firewall_report"> </a></span></span>

<span data-ttu-id="27d57-144">В Skype для бизнеса Server 2015 имеется потенциально сложный набор правил брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="27d57-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="27d57-145">Средство планирования снижает эту сложность, создавая отчет, который подробно определяет все требования брандмауэра на основе критериев ввода конструктора.</span><span class="sxs-lookup"><span data-stu-id="27d57-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="27d57-146">Администратор брандмауэра ИТ-инфраструктуры сможет использовать этот отчет для настройки и определения необходимых правил.</span><span class="sxs-lookup"><span data-stu-id="27d57-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="27d57-147">С точки зрения управления брандмауэром, отчет следует тщательно проанализировать, чтобы убедиться, что нет конфликтов с выходом правил брандмауэра и что не существует политик или процедур, которые могут быть нарушены.</span><span class="sxs-lookup"><span data-stu-id="27d57-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![Отчет администратора брандмауэра](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="27d57-149">Просмотр отчета DNS</span><span class="sxs-lookup"><span data-stu-id="27d57-149">Review the DNS Report</span></span>
<span data-ttu-id="27d57-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="27d57-150"><a name="DNS_Report"> </a></span></span>

<span data-ttu-id="27d57-151">В отчете DNS, который входит в отчет администратора, подробные сведения о всех рекомендуемых и известных записях для службы доменных имен (DNS) во внутренней, демилиаторской и внешней сетях.</span><span class="sxs-lookup"><span data-stu-id="27d57-151">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks.</span></span> <span data-ttu-id="27d57-152">Если конструктор выполнил изменения сетевой схемы, а все IP-адреса и полное доменное имя (FQDNs) определены в производственных значениях, отчет DNS предоставляет отличный ресурс конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27d57-152">If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource.</span></span> <span data-ttu-id="27d57-153">Этот отчет также может служить рабочим документом по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="27d57-153">This report can also serve as an operational troubleshooting document.</span></span>

![Отчет администратора DNS](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="27d57-155">Группа управления DNS должна тщательно изучить отчет DNS, чтобы убедиться, что нет ошибок, которые могут вызвать трудности во время развертывания или усложнять сеанс устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="27d57-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="27d57-156">См. также</span><span class="sxs-lookup"><span data-stu-id="27d57-156">See also</span></span>
<span data-ttu-id="27d57-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="27d57-157"><a name="DNS_Report"> </a></span></span>

[<span data-ttu-id="27d57-158">Просмотр отчетов администратора</span><span class="sxs-lookup"><span data-stu-id="27d57-158">Reviewing the Administrator Reports</span></span>](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
