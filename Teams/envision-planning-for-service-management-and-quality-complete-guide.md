---
title: Plan for service management guide for Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Deliver high-quality Teams user experience by managing service, network, and endpoint health and defining operational and Quality Champion roles.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cccd06cd9bd5ee458497fbb41db56955bb9a5ee9
ms.sourcegitcommit: d70e5a5e7d05a2226c1d011895fb12187d73fad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2018
---
# <a name="plan-for-service-management-and-quality"></a>Plan for service management and quality

This document is about the Envision phase for Microsoft Teams.
 
## <a name="introduction"></a>Введение

This content will provide an overview of the requirements that are necessary to deliver and maintain a high-quality Microsoft Teams deployment. You can help ensure a successful deployment by planning for service management and quality during the Envision phase, before your first pilot or production deployment.

The guidance is organized into the following sections:

-   First is an overview of user experience and the key components that underpin quality. This highlights the areas to focus on prior to onboarding to Microsoft Teams.

-   Second, guidance is given for planning a support model to manage Microsoft Teams prior to the first user pilot or production deployment. This section describes the tasks that need to be performed on a regular basis to maintain a quality Teams deployment. In addition, this section introduces you to further guidance which you can use to start understanding and operationalizing these tasks.

-   Third, specific guidance helps with planning your network and endpoints in your organization to support Microsoft Teams.

-   Lastly, next steps are summarized with references to related content.

## <a name="key-components-that-affect-user-experience"></a>Key components that affect user experience

The key components that affect user experience will be reviewed in this section. Before reviewing the key components, it’s critical that you understand user experience and its importance in realizing your organization’s business goals. Let’s review how we define the user experience first.

### <a name="user-experience-defined"></a>User experience defined

Business goals can be realized when you deploy Microsoft Teams and incorporate communications into your business processes to enhance their workflow. Quality drives adoption and usage: if your organization delivers a high-quality service that delights people, then individuals and teams can gain confidence and find new and innovative ways of using the service that drive business benefits.

At the heart of this is the user’s experience with Teams—the person’s emotions and attitudes toward the service. So what contributes to the user experience? It ranges from users’ knowing how to use Teams and incorporating it into their daily workflow to experiencing exceptional call quality and being able to connect reliably, regardless of where they are. User experience is very broad in nature; this document focuses only on those elements that can be controlled by your organization.

There are specific requirements to the deployment that are critically important to deliver a fantastic user experience—especially when using the Cloud Voice features in Teams. It is critical to treat Microsoft Teams as a first-class citizen with other communication and collaboration investments, prioritizing real-time traffic accordingly. The following section gives an overview of the key components that affect user experience. In further sections, we will provide you guidance on how to start planning to deploy and maintain the key components that comprise quality.

### <a name="key-components-of-quality"></a>Key components of quality

An organization or supporting partner should start planning for three key components during the Envision phase of a Teams deployment: service management, network, and endpoints. The combination of all three areas is fundamental to the quality of the user experience.

![Diagram describing the 3 components of quality, and how service management overlaps all 3 components.](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png)

#### <a name="service-management"></a>Service management

Service management can be divided into two distinct categories of responsibility:

-   **Microsoft responsibility**. Microsoft is responsible for the infrastructure components that the Office 365 service comprises. Microsoft is accountable to customers to ensure that any of their users connecting to Teams is provided with a reliable and high-quality experience.

-   **Customer responsibility**. You and your organization are responsible for managing various aspects of the Office 365 service, on-premises network, and user endpoints. For example, as new IP addresses are added to Office 365, you must update the appropriate firewalls to allow communication to the new endpoints to avoid user disruption.

For detailed guidance for service management planning, see [Planning for Service Management](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-service-management).

#### <a name="network"></a>Сеть 

In most organizations, networks were initially designed to provide access to data and applications that resided in their datacenters. Cloud-based applications like Office 365 require changes to these networks to support the new access and data flows that Teams requires. Before you can enable users for Teams in your organization, you must evaluate and optimize your current network. This is critically important when leveraging cloud voice capabilities.

In traditional networks, users will need to traverse the perimeter networks of an organization to access Teams. Many organizations will have security-based devices such as proxy servers, firewalls, and VPNs that can block, impede, or provide an unoptimized path for network traffic.

Furthermore, the core internal networks need to be optimized and right-sized to provide sufficient capacity and quality for supporting the Teams workloads, including real-time media. You can use bandwidth planning, remediation, and optimization to help ensure your network provides a high-quality and efficient path to Office 365.

For detailed guidance about network planning, see [Planning for Network Quality](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-network-quality).

#### <a name="endpoints"></a>Конечные точки

Microsoft Teams supports a variety of endpoints. From PCs to tablets to phones, you can access Teams anywhere from virtually any device.

To give your users the best experience possible, you need to consider these important aspects during the Envision phase: Do your endpoints meet the Teams hardware and software requirements? Have you configured and optimized endpoints to support Wi-Fi networks? Which devices will you use to make and receive voice calls? Are those devices optimized for Teams?

For detailed guidance about endpoint planning, see [Planning for Endpoint Quality](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Plan for service management

Service management is a broad topic that covers day-to-day operations of the Microsoft Teams service after it has been deployed and enabled for users. The Teams service encompasses Microsoft Office 365 and the infrastructure components that are deployed on-premises (for example, networking).

The notion of service management is most likely not a new concept for most organizations. You probably have already implemented processes and tasks that are associated with existing services. That said, you can probably augment what you have in place when you plan for service management today to support Microsoft Teams in the future.

Service management encompasses all the activities and processes involved in managing Microsoft Teams end to end. As described earlier, some components of service management—the infrastructure components that the Office 365 service itself comprises—are Microsoft’s responsibility, whereas the customer is accountable to its users to manage the various aspects of Teams, the network, and endpoints they provide. This section of the document will focus on the customer’s responsibility from a service management perspective.

![Diagram describing the 3 components of qualilty, and how service management overlaps all 3 components. With a focus on Service Mangement.](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png)

### <a name="introduction-to-the-operations-guide"></a>Introduction to the Operations Guide 

**What**, **Who**, and **How** are three important questions that need to be answered when it comes to service management.

You can use the Operations Guide [Link to Operations Guide] to help you address all three of these questions. The guide provides a list of activities to be performed on a daily, weekly, monthly, and as-needed basis. These activities and tasks are critical for maintaining a high-quality Teams deployment. Determining who will be responsible for performing specific activities in service management is a critical aspect of your planning that you need to do early in the Envision phase to ensure a successful deployment. After you’ve figured out the tasks and activities, they need to be understood and followed by the groups or individuals that you assign to them. The Operations Guide provides knowledge and guidance for how to perform each of the tasks, and/or references to outside content.

### <a name="operational-role-mapping"></a>Operational role mapping

Planning for service management early is a critical milestone, because the operations phase begins when the first pilot users are enabled. The project team must review and agree on the tasks and activities required, identify the team that’s responsible for each operational task, and then get a commitment and sign-off from each respective team.

After sign-off is complete, the responsible team must then start operationalizing these roles and responsibilities. This might include training and readiness, updating the staffing model, or ensuring that external partners are ready to deliver.

Mapping operational roles early in the Envision phase enables all teams to start their operational tasks during the pilot, and ramp up operations and make sure that everything is ready after the deployment starts.

The Operations Guide provides a list of common tasks mapped to typical roles that should be valid in most scenarios. You need to customize these responsibilities to work for your organization.

### <a name="the-quality-champion-role"></a>The Quality Champion role

A group or individual needs to be accountable for quality in all organizations. This is the most important role in service management. The Quality Champion is a customer role that's assigned to a person or group who is passionate about their users' experience. This role requires the skills to identify trends in the environment and the sponsorship to work with other teams to drive remediation. The best candidate for the Quality Champion is typically the customer service owner, who—depending on the organization’s size and complexity—could be any person or group who is passionate about user experience.

The Quality Champion leverages existing tools and documented processes, such as the Call Quality Dashboard (CQD) and the Quality Experience Review Guide, to monitor user experience, identify quality trends, and drive remediation where needed. The Quality Champion works with the respective teams to drive remediation actions, reporting to a steering committee on their progress and open issues.

The tasks and activities associated with the role have been documented in the Operations Guide. This role should be assigned early in the Envision phase. A key step in operationalizing the role of Quality Champion is gaining the knowledge required for the role and ensuring the prerequisites are in place to deliver on the tasks. A key task for this role is running a regular Quality Experience Review.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introduction to the Quality Experience Review Guide

The Quality Experience Review Guide has a set of activities that assess and provide remediation guidance in key areas that have the greatest impact for improving user experience as shown in the figure below.

![A diagram that indicates the key areas that are examined during a quality experience review.](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png)

By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect user experience. Most user-experience problems encountered in a deployment can be grouped into the following categories:

-   Incomplete firewall or proxy configuration

-   Poor Wi-Fi coverage

-   Insufficient bandwidth

-   VPN

-   Use of unoptimized or built-in audio devices

-   Problematic subnets or network devices

The guidance provided in the Quality Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact. Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.

We highly recommend that you nominate the Quality Champion early on. After being nominated, they should start to familiarize themselves with the content in the Quality Experience Review Guide.

The Quality Experience Review Guide can be found [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

## <a name="plan-for-network-quality"></a>Plan for network quality 

Planning for network quality will be the focus for the following section.

![Diagram describing the 3 components of quality, and how service management overlaps all 3 components. With a focus on Network.](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png)

As previously mentioned, planning for network quality prior to onboarding to Microsoft Teams is critical. For further guidance for network readiness, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network).

В большинстве организаций сетей может включать в себя управляемые и неуправляемые сетей.

Managed networks are components of the network infrastructure that an organization has direct control over. As a result, managed networks have a direct influence on the quality that can be provided to real-time traffic workloads.

Conversely, unmanaged networks are segments of the network that a customer has limited control, or no control, over.

Internet connections between the organization and Office 365 are networks where a customer has limited control. The networks are managed by an ISP, but organizations should be able to influence the quality of the network by upgrading their bandwidth, advocating for route optimizations, or—if all else fails—switching ISPs.

Home networks or networks in hotels or coffee shops are examples of networks where a customer has no control.

In the following sections, we will focus on the quality requirements of managed networks.

### <a name="key-network-planning-areas"></a>Key network planning areas

The following sections focus on the important areas for delivering a high-quality network.

> [!NOTE]
> Many networks evolve over time due to upgrades, expansion, or other business requirements. Убедитесь, что рабочих процессов на месте для поддержки этих областей в процессе планирования управления службы.

#### <a name="bandwidth"></a>Bandwidth

Bandwidth planning is a critical aspect of the network readiness activity. Ensuring that there's enough bandwidth for the Microsoft Teams workloads is imperative. Должны иметь возможность право размера существующего сети, необходимо понимать, что в настоящее время наполнения, текущего использования ресурсов и — в конечном счете, оставшихся наличной пропускной способности.

To measure current utilization, you need to monitor the network. This measurement can then be used as the starting point for bandwidth planning. Кроме того сети должны постоянно отслеживаться во время развертывания и после развертывания, чтобы убедиться, что сеть достаточно подготовлен.

> [!NOTE]
> When monitoring network utilization, it’s important to avoid using averages over the day. These averages can include non-core hours that skew the result. Averages can hide peak periods and mask an underlying problem.

The [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) helps you determine and organize network requirements for your deployment in just a few simple steps. By using the tool to gather your organization's networking details and Cloud Voice usage, you can get an approximate calculation of the network requirements you’ll need for your Cloud Voice deployment, manage and export these details for reporting, and view areas for further investigation and next steps.

#### <a name="quality-of-service-qos"></a>Quality of service (QoS)

QoS should be implemented on all segments of the managed network, even networks that have been adequately provisioned for bandwidth. In the latter case, QoS acts as a risk mitigation in the event of unanticipated network load. When QoS is implemented, voice traffic will be prioritized so that these unanticipated events don’t affect quality.

A QoS implementation should include areas of the network, from the endpoint all the way up to the egress points and from the egress points back to the endpoint. Это гарантирует, что передачи голосовых данных назначаются приоритеты в обоих направлениях. Качество обслуживания должен быть реализован на другое проводное и сети Wi-Fi.

Для реализации качества обслуживания в сети, следующие рекомендации могут помочь [Качества обслуживания в группах Майкрософт](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)

#### <a name="proxy-servers"></a>Прокси-серверы

Many organizations view traffic destined for the internet as a security risk, and they mitigate this risk by monitoring and evaluating traffic at the egress points in the network. Прокси-серверы — это класс устройств, которые могут быть развернуты в соответствии с этим требованиям.

Прокси-сервер могут вызвать проблемы при выполнении проверки сетевых пакетов или изменение полезных данных. This can lead to call setup failures, dropped calls, and poor call quality. Если в режиме реального времени мультимедиа принудительно проходят через прокси-сервер, стек мультимедиа в группах принудительно не TCP могут сократить качества. UDP-ПОРТ всегда является предпочтительным по протоколу TCP.

Кроме того, прокси-сервер может не предназначено для обработки дополнительной нагрузки Office 365 и специально рабочих нагрузок группами Майкрософт, включая мультимедиа в режиме реального времени.

Due to the potential problems a proxy server can introduce, and these additional capacity concerns, Microsoft recommends bypassing the proxy server and making a direct connection to Office 365.

Конфигурация, необходимая для обхода прокси-сервера меняется в зависимости от поставщиков, но общий подход обычно включает в себя обновление файла (PAC) Автоматическая настройка прокси-сервера. Файл PAC представляет собой файл конфигурации, описывающего какие трафик проходит через прокси-сервер и трафик обходит его.

Some proxy server vendors provide an automated process for ensuring the configuration is up to date. Если поставщик не предоставляет этот автоматический процесс, можно загрузить обновленный файл PAC из <https://aka.ms/o365proxies>.

[Прокси-серверы для Скайп для бизнеса в Интернете и рабочих групп](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Брандмауэры

Убедитесь, что справа порты и протоколы открыть, чтобы все Office 365 IP-адреса и URL-адреса требуется для получения доступа к группами Майкрософт. Также важно для развертывания высокого качества. Просто вызов или выполняется присоединение к конференции не достаточно необходимо убедиться, что брандмауэр настроен правильно.

Если только TCP открыта в брандмауэре, сеанс будет установлено, но предпочитаемый транспорта (UDP-ПОРТ) не согласовано. TCP и UDP должны быть открыты для брандмауэра для обеспечения работы пользователей.

Из-за его с сохранением состояния характер TCP не будет предпочтительным для мультимедиа в режиме реального времени и предоставляется только в качестве транспорта сети восстановление размещения для групп Майкрософт. С TCP если задержка пакетов или убытков, пакеты должны быть повторно до их в случае подтверждено. Это может привести к мультимедиа пакетов, которые больше не соответствующих за счет своевременного текущего пакетов мультимедиа. Клиент группы пользователя пытается увеличить аудио и может осуществлять звуковой артефактов в зависимости от того, в сети. С помощью дополнительных затрат на TCP обычно приемлемой качества, могут перейти низкого уровня пользовательского интерфейса. По этой причине без сведений о состоянии сети транспорта UDP-ПОРТ является обязательным.

Полное руководство для открытия брандмауэра для групп Майкрософт предоставляется в статье [Office 365 URL-адреса и диапазоны IP-адресов](https://aka.ms/o365ips) .

После открытия брандмауэра, можно использовать [Средство оценки производительности сети Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=53885) для проверки подключения для возможности голосовой связи облака.

> [!IMPORTANT]
> Microsoft Office 365 IP-адреса и URL-адреса будут изменяться со временем. При планировании управления службы важно обеспечить рабочего процесса на месте и группы отвечает для наблюдение за [Office 365 URL-адреса и диапазоны IP-адресов](https://aka.ms/o365ips) и выполнения обновлений соответствующим образом.

#### <a name="local-internet-egress"></a>Локального исходящего трафика Интернета

Многие сети были предназначены для использования сервера-концентратора и резервный топологии. В этой топологии трафика из Интернета обычно проходят через глобальной сети для центрального центра обработки данных перед его выскочит (egresses) к Интернету. Часто это централизовать сетевых устройств безопасности с целью уменьшения общую стоимость.

Доставить назад трафика глобальной сети увеличивает задержку и имеет отрицательное влияние на качество и удобство работы пользователей. Поскольку группами Майкрософт выполняется в корпорации Майкрософт большой глобальной сети, нет часто в сетевой папке авторами закрыть для пользователя. Пользователь будет вероятнее всего получить более высокую производительность, egressing из локального точки internet почти их расположения и вход в систему сети optimized голосовой связи, как можно скорее. Для некоторых видов нагрузки DNS-запросы используются для отправки трафика ближайший сервера переднего плана. В таких случаях важно, что при использовании локального выходной точке, сопряжено с локального разрешения DNS.

Оптимизация сетевой путь к глобальной сети корпорации Майкрософт улучшить производительность и в конечном счете оптимального для пользователей. Дополнительные сведения см в блоге [Начало наиболее подключения и производительности в Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Виртуальные частные сети обеспечения ценных службы на многие организации. К сожалению они обычно не предназначена или настроить для поддержки мультимедиа в режиме реального времени. Некоторые VPN также могут не поддерживать UDP-ПОРТ. Виртуальные частные сети также предоставляют дополнительный уровень шифрования на основе трафика мультимедиа по умолчанию. Кроме того возможность подключения к службе группами Майкрософт может оказаться эффективным из-за фиксации Сверхтонкая трафика через устройство VPN. Кроме того они не могут обязательно с точки зрения емкости для учета предполагаемых нагрузок, которые требуют группами.

Рекомендуется предоставить альтернативный маршрут, который обходит виртуальной частной сети для трафика группами. Обычно это называется split туннель VPN. Туннелирование способом разделения этого трафика для Office 365 не проходят через VPN-Подключение, но будет перейти непосредственно к Office 365. Это изменение будет иметь положительное влияние на качество, но также предоставляет дополнительный преимущества уменьшения нагрузки из сети организации и VPN-устройства.

Чтобы реализовать split туннель, обратитесь к поставщику сети VPN для сведений о конфигурации.

#### <a name="wi-fi"></a>Wi-Fi

Как виртуальных Частных сетей Wi-Fi не обязательно предназначена или не настроен для поддержки мультимедиа в режиме реального времени. Планирование и/или оптимизация, сети Wi-Fi для поддержки команд — это особенно важно для развертывания контроля качества.

Существует ряд факторов, которые следует учитывать для оптимизации сети Wi-Fi.

-   Реализация качества обслуживания и мультимедиа Wi-Fi (WMM) для обеспечения этого трафика мультимедиа начало их приоритета соответствующим образом через сети Wi-Fi.

-   Планирование и оптимизация W-Fi панелей и доступа выберите размещение. Диапазон 2,4 ГГц может обеспечить достаточное количество возможности в зависимости от расположения точки доступа, но точки доступа, часто влияют другие пользовательские устройства, которые используются в этом диапазоне. Диапазон 5 ГГц больше подходит в режиме реального времени мультимедиа из-за их высокой плотности диапазон, но требуется несколько точек доступа для получения достаточно покрытия. Конечные точки также должны поддерживать этот диапазон и настроен соответствующим образом использовать эти полосы.

-   Если сети Wi-Fi появление развернуты, рассмотрите возможность реализации управления диапазона. Управление полосой — это метод, реализованный Wi-Fi поставщиков, влияющих на централизованной двойного клиентам использовать диапазон 5 ГГц.

-   Перекрытие каналов — при точки доступа же канала слишком близко друг к другу, они могут привести к перекрытие сигнала и случайно конкурируют приведет к недопустимый интерфейс для пользователя. Убедитесь, что точка доступа, которые рядом друг с другом на каналы не повторять.

Каждого беспроводной поставщика имеет свой собственный рекомендации по развертыванию беспроводной решения. Мы рекомендуем, обратитесь к своему поставщику для конкретные инструкции.

### <a name="network-readiness-assessment"></a>Оценка готовности сети

Часть действий по подготовке сети включает оценки сети. После выполнения планирования и настройки, оценки поможет вам Общие сведения о базовой качества сети перед выполнением встроенного пользователей группам Microsoft. Результаты оценки также поможет вам определить и определять приоритеты усилия по устранению проблем перед включением для групп пользователей.

Оценки сети должны быть выполнены для обоих проводной сети и сетей Wi-Fi для всех зданий, которые разрешены для облачных возможности голосовой связи в группах.

Оценки сети может осуществляться с помощью партнера корпорации Майкрософт, средства сторонних производителей или [средство оценки производительности сети Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=53885). Мы также представлено руководство о том, как выполнить оценку, с помощью средство оценки производительности сети Майкрософт в составе указаниям по подготовке [здесь](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11)...

## <a name="plan-for-endpoint-quality"></a>Планирование качества конечной точки

Как видно из приведенной ниже диаграмме, конечные точки являются важными стандартный блок в поддержке качества взаимодействия для конечных пользователей.

![Схема, описывающая 3 компоненты качества, а также как служба управления перекрывается всех компонентов 3. С фокусом в конечных точках.](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png)

Конечные точки группы Microsoft можно запустить на многих устройствах, включая ПК, Макинтош, планшетные ПК и мобильных устройств. При работе не только включает устройство, но как пользователь подключается к устройства — например, с помощью встроенных устройства микрофона или динамика, со звукоизоляцией очистить или оптимизированный гарнитуры. С помощью оптимизированного гарнитуры можно расширить общего взаимодействия с пользователем.

Следующие рекомендации по планированию реализации конечной точки поможет вам убедитесь, что ваша организация успешного входящая опыт работы с группами.

### <a name="endpoint-capability"></a>Возможность конечной точки

— Это первая часть планирования для обеспечения все компьютеры и другие устройства в организации можно запустить группами Майкрософт. Это включает в себя не только ниже описаны требования к оборудованию, а также основные сведения о else ПК действия в фоновом режиме. Многие организации выполнить другое программное обеспечение, включая системы обнаружения вторжений и программное обеспечение защиты от вредоносных программ, которое может повлиять на производительность базового устройства.

Группами Майкрософт имеет клиенты доступных веб-приложений, настольных систем (Windows и Mac) и мобильные устройства (Android, iOS и Windows Mobile). Сведения о требованиях к программному обеспечению для каждой платформы видеть [Получить клиентов для групп Майкрософт](https://docs.microsoft.com/microsoftteams/get-clients).

### <a name="endpoint-firewalls"></a>Конечная точка брандмауэров

Клиентские брандмауэры могут оказывают значительное влияние на взаимодействие с пользователем. Клиентские брандмауэры могут повлиять на качество звонка в дополнение к препятствует созданию звонка. Настройте соответствующие исключения брандмауэра клиента, основываясь на информации в [Office 365 URL-адреса и диапазоны IP-адресов](https://aka.ms/o365ips). Независимых поставщиков будут иметь конкретные инструкции по созданию исключения.

> [!NOTE]
> Группами Майкрософт будет автоматически обновлять брандмауэра Windows с конфигурацией соответствующие брандмауэра.

### <a name="wi-fi-recommendations-for-endpoints"></a>Рекомендации по Wi-Fi для конечных точек

Планирование и развертывание оптимизированный сети Wi-Fi для поддержки рабочих нагрузок в режиме реального времени в группах Microsoft потребует значительные планирования. В следующих разделах представлены некоторые общие рекомендации, помогающие избежать некоторых распространенных ошибок при планировании для конечных точек.

#### <a name="wi-fi-drivers"></a>Драйверы Wi-Fi

Некоторые драйверы Wi-Fi может быть проблематичным. Например драйвер может быть очень агрессивные поведение перемещения между точками доступа, качество процента звонков низкого качества. Это значение не распространенный вариант, но не важно, чтобы убедиться, что обновлены и тестирование перед развертыванием, драйверы Wi-Fi на персональном Компьютере.

#### <a name="wi-fi-bands"></a>Полосы Wi-Fi

Существует в основном два типа полос Wi-Fi сегодня оборудования, 2,4 ГГц и 5,0 ГГц. Если организация предоставляет обеих полос, следует настроить параметры драйвера к выбору 5.0 ГГц. Этот диапазон намного выше плотность терминах пропускной способности и меньше влияет помехи, видимых 2,4 ГГц. Эта рекомендация предполагается, что должным образом optimized 5.0 ГГц сети.

#### <a name="wi-fi-radio-type"></a>Тип радио Wi-Fi

Планирование для устройств, поддерживающих новые типы радио Wi-Fi. Можно получить очень хорошую производительность Wi-Fi, если использовать 802.11ac или более поздней версии на устройствах, подготовкой.

#### <a name="wireless-avoidance"></a>Избежание беспроводной сети

Некоторые организации предпочитают полностью избежать Wi-Fi. В некоторых случаях данное руководство осуществляется через рекомендации, чтобы пользователи могли напрямую подключаться к проводной сети. В некоторых случаях порядок привязки к сети могут иметь предпочитаемое беспроводное подключение и продолжить использовать это подключение, несмотря на то, что компьютер подключен к проводное подключение. Чтобы избежать этого случайных, настройте порядок привязки, чтобы избежать этого сценария.

#### <a name="80211-power-save-protocol"></a>протокол энергосбережения 802.11

Если организация использует точки беспроводного доступа или маршрутизаторы, не поддерживающие мощности 802.11 сохранение протокола, может привести к пропущенные звонки или процента звонков низкого качества качества группами Майкрософт, работающих на устройствах Windows. Если не удается обновить точку беспроводного доступа или маршрутизаторы, следует обновить план электропитания Windows Параметры на устройствах, на которых выполняется от батарей. Дальнейший подробной указаний в следующей [статье технической поддержки](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Устройства для групп

Группами Майкрософт можно использовать для собраний или с телефонной системой. При использовании этих функций, устройство интерфейс, используемый для групп играет важную роль в работе пользователей.

С помощью встроенных ПК Динамики и микрофон может показаться приемлемой для пользователя, который имеет этой конфигурации. Но обычно эти устройства не оптимизирован для отмены шума и любого типа шума может иметь нижестоящие воздействия на другие пользователи на звонок. Максимальное использование всех возможностей устройства, оптимизированные для следующих сценариев поможет обеспечить высокое качество взаимодействия.

Каждое устройство должно для удовлетворения потребностей пользователей. Вам потребуется настроить устройств, например гарнитуры для различных пользователей и примеры использования в организации. Сопоставление пользователя для устройств упражнения необходимо выполнить как часть процесса планирования.

После выбора устройства, включите их в план пилотного тестирования для окончательного проверки. Использование опросы во время пилотного проекта для сбора отзывов для обеспечения стратегии устройство является оптимальным.

На этом этапе рекомендуется использовать звуковых устройств, которые были сертифицированный через Скайп для программа сертификации предприятия. Чтобы найти устройств, сертифицированных по программе, обратитесь к каталог решений [Устройства USB, сертифицированном для Скайп для бизнеса](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

Для получения дополнительных сведений см [клиентов и устройств - курс обучения для проверки готовности к](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Обновления клиента

Одним из основных преимуществ группами Майкрософт — это, что клиент будет храниться в актуальном состоянии автоматически. Клиенты на ПК или Mac обновляются с помощью фонового процесса, который ищет новые построения и файлы для загрузки новый клиент при простое приложение. Размер загрузки клиента примерно составляет 100 МБ.

Организации не содержит элемент управления или доступ к параметру политики для управления процессом обновления. Для снижения риска проблема, которая может обнаруживать в более новое построение последнюю известную версию, хранимых на конечной точке. Если проблема связана с новое построение, службы группами Майкрософт может вернуться конечной точки для предыдущей версии автоматически.

## <a name="next-steps-and-references"></a>Далее действия и справочные материалы

В таблице приведена сводка по действиям при планировании со ссылками на связанный контент.

| Область | Сведения | Справочные материалы |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Планирование службы управления | Проведение упражнения сопоставления действующие роли <br/> Утверждение запроса из ответственность рабочих групп <br/> Проверки готовности к роли | [Руководство пользователя](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) |
| | Используют Champion(s) качества <br/> Качество Champion готовности| [Узнайте, CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Руководство по решению для качества взаимодействия](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) |
| | Установка шаблонов анализа качества взаимодействия <br/> Отправка файла построения | [Шаблоны QERLite](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true) <br/> [Построение Отправка информации](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?ui=en-US&rs=en-US&ad=US#upload-building-information)|
| Планирование качества сети | Запустите планировщик работы сети | [Планировщик работы сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Реализация качества обслуживания | [Качество обслуживания в группах Майкрософт](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| | Обход прокси-сервера | [Руководство по прокси-сервера](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | Реализация разделения туннель через VPN | [Руководство по туннель Split VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Оптимизация сети Wi-Fi для мультимедиа в режиме реального времени  | Обратитесь к третьей стороны поставщиков |
| | Реализация локального исходящего трафика Интернета | [Выходной локальная интрасеть](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Реализация подключение к сети <br/> Проверка подключения к сети | [URL-адреса Office 365 и IP-адреса](https://aka.ms/o365ips) |
| | | [Средство оценки производительности сети](https://www.microsoft.com/en-us/download/details.aspx?id=53885) |
| | Оценка сети | [Оценка готовности сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Планирование качества конечной точки | Обновление конечной точки брандмауэров | [URL-адреса Office 365 и IP-адреса](https://aka.ms/o365ips) |
| | Проверка требований к программному обеспечению | [Получение клиентов для групп Майкрософт](https://docs.microsoft.com/microsoftteams/get-clients) |
| | Реализовать рекомендации конечной точки Wi-Fi | Обратитесь к третьей стороны поставщиков |
| | Проведение пользователя к устройствам сопоставление <br/> Подготовка устройств и их пилотный проект | [Клиентов и устройств - курс обучения для проверки готовности к](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Каталог устройства](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |