---
title: Параметры подключения через ДНР
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Узнайте больше о Teams звонков (ЗВОНКОВ) и решениях, принятых в вашей организации.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354525"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="86242-103">Параметры подключения через ДНР</span><span class="sxs-lookup"><span data-stu-id="86242-103">PSTN connectivity options</span></span>

<span data-ttu-id="86242-104">Корпорация Майкрософт предоставляет полный доступ к Exchange УАПС для вашей организации с помощью телефонная система.</span><span class="sxs-lookup"><span data-stu-id="86242-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="86242-105">Однако для того чтобы пользователи могли звонить за пределы организации, необходимо подключить телефонная система к телефонной сети общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="86242-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="86242-106">В этой статье данная статья посвящена вариантам подключения через ДНР.</span><span class="sxs-lookup"><span data-stu-id="86242-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="86242-107">Дополнительные сведения о голосовых решениях Майкрософт, в том телефонная система функции, см. в Teams [решения.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="86242-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="86242-108">Чтобы подключить телефонная система к STN, можно выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="86242-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="86242-109">[**План звонков**](#phone-system-with-calling-plan).</span><span class="sxs-lookup"><span data-stu-id="86242-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="86242-110">Облачное решение, в качестве оператора связи по STN — Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="86242-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="86242-111">[**Прямая маршрутная маршрутия**](#phone-system-with-direct-routing), которая позволяет использовать собственный оператор STN, подключив контроллер границы сеанса (SBC) к телефонная система.</span><span class="sxs-lookup"><span data-stu-id="86242-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="86242-112">[**Оператор Подключение**](#phone-system-with-operator-connect), который в настоящее время доступен только в **режиме предварительной версии.**</span><span class="sxs-lookup"><span data-stu-id="86242-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="86242-113">Операторы Подключение, если ваш оператор является участником программы microsoft Operator Подключение, они могут управлять звонками по ЗВОНКОВ через ПСОП и контроллерами границ сеанса.</span><span class="sxs-lookup"><span data-stu-id="86242-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="86242-114">Вы также можете выбрать сочетание параметров, которое позволяет создать решение для сложной среды или управлять многошаговой миграцией.</span><span class="sxs-lookup"><span data-stu-id="86242-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="86242-115">Следует помнить, что эти параметры влияют на телефонная система функций.</span><span class="sxs-lookup"><span data-stu-id="86242-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="86242-116">Дополнительные сведения см. в [статье Сведения о конфигурации](#configuration-considerations) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="86242-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="86242-117">телефонная система с планом звонков</span><span class="sxs-lookup"><span data-stu-id="86242-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="86242-118">телефонная система с планом звонков — это облачное решение Майкрософт для Teams пользователей.</span><span class="sxs-lookup"><span data-stu-id="86242-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="86242-119">Это самый простой вариант, который подключается телефонная система к STN.</span><span class="sxs-lookup"><span data-stu-id="86242-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="86242-120">При этом корпорация Майкрософт выступает в качестве оператора связи по STN, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="86242-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![На схеме 1 показаны телефонная система с планом звонков](media/voice-solutions-simple.png)

<span data-ttu-id="86242-122">Если вы отвечаете да, телефонная система с помощью плана звонков:</span><span class="sxs-lookup"><span data-stu-id="86242-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="86242-123">План звонков доступен в вашем регионе.</span><span class="sxs-lookup"><span data-stu-id="86242-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="86242-124">Не требуется хранить текущий оператор ПСПС.</span><span class="sxs-lookup"><span data-stu-id="86242-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="86242-125">Вы хотите использовать доступ к STN, управляемый Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="86242-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="86242-126">С помощью этого параметра:</span><span class="sxs-lookup"><span data-stu-id="86242-126">With this option:</span></span> 

- <span data-ttu-id="86242-127">Вы получаете Телефон (Майкрософт) с добавленными планами внутренних или международных звонков, которые позволяют звонить на телефоны по всему миру (в зависимости от уровня обслуживания).</span><span class="sxs-lookup"><span data-stu-id="86242-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="86242-128">Развертывание или обслуживание локального развертывания не требуется, так как план звонков работает &mdash; вне Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86242-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="86242-129">Примечание. При необходимости вы можете подключить поддерживаемый пограничный контроллер сеанса (SBC) с помощью прямой маршрутировки для обеспечения связи со сторонними УАКС, аналоговыми устройствами и другими сторонними телефонными устройствами, которые поддерживаются SBC.</span><span class="sxs-lookup"><span data-stu-id="86242-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="86242-130">Для этого параметра требуется непрерывное подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86242-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="86242-131">Дополнительные сведения о плане звонков см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="86242-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="86242-132">Какой план звонков подходит для вас?</span><span class="sxs-lookup"><span data-stu-id="86242-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="86242-133">Как купить план звонков</span><span class="sxs-lookup"><span data-stu-id="86242-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="86242-134">Доступность планов звонков в различных странах и регионах</span><span class="sxs-lookup"><span data-stu-id="86242-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="86242-135">Настройка плана звонков</span><span class="sxs-lookup"><span data-stu-id="86242-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="86242-136">телефонная система с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="86242-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="86242-137">Этот параметр подключается телефонная система к телефонной сети с помощью прямой маршрутии, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="86242-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![На схеме 5 телефонная система с прямой маршрутией](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="86242-139">Если вы отвечаете да на следующие вопросы, то телефонная система с direct Routing — это правильное решение.</span><span class="sxs-lookup"><span data-stu-id="86242-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="86242-140">Вы хотите использовать Teams с телефонная система.</span><span class="sxs-lookup"><span data-stu-id="86242-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="86242-141">Необходимо сохранить текущего оператора связи через ОКП.</span><span class="sxs-lookup"><span data-stu-id="86242-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="86242-142">Вы хотите комбировать маршрутику с некоторыми звонками через план звонков, некоторые из них через оператора связи.</span><span class="sxs-lookup"><span data-stu-id="86242-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="86242-143">Необходимо работать со сторонними УАКС и оборудованием, например накладными страницами, аналоговыми устройствами и так далее.</span><span class="sxs-lookup"><span data-stu-id="86242-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="86242-144">С помощью этого параметра:</span><span class="sxs-lookup"><span data-stu-id="86242-144">With this option:</span></span>

- <span data-ttu-id="86242-145">Вы подключали собственный поддерживаемый контроллер границы сеанса (SBC) к телефонная система без необходимости в дополнительном локальном программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="86242-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="86242-146">Вы можете использовать практически любой оператор телефонии с телефонная система.</span><span class="sxs-lookup"><span data-stu-id="86242-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="86242-147">Вы можете настроить этот параметр и управлять им, а также настроить его и управлять им может оператор или партнер (спросите, предоставляет ли этот параметр ваш оператор или партнер).</span><span class="sxs-lookup"><span data-stu-id="86242-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="86242-148">Вы можете настроить взаимодействия между телефонным оборудованием, таким как стороннее УАКС и аналоговые устройства, а также использовать &mdash; &mdash; телефонная система.</span><span class="sxs-lookup"><span data-stu-id="86242-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="86242-149">Для этого параметра требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="86242-149">This option requires the following:</span></span>

- <span data-ttu-id="86242-150">Непрерывное подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86242-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="86242-151">Развертывание и обслуживание поддерживаемых SBC.</span><span class="sxs-lookup"><span data-stu-id="86242-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="86242-152">Контракт со сторонним оператором.</span><span class="sxs-lookup"><span data-stu-id="86242-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="86242-153">(Если не развернуто как параметр для подключения к сторонним УАП, аналоговым устройствам или другому телефонном оборудованию для пользователей, которые находятся телефонная система с планом звонков.)</span><span class="sxs-lookup"><span data-stu-id="86242-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="86242-154">Дополнительные сведения о прямой маршрутике см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="86242-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="86242-155">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86242-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="86242-156">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86242-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="86242-157">Управление политиками голосовой маршрутии для использования с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="86242-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="86242-158">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86242-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="86242-159">Список пограничных контроллеров сеансов, сертифицированных для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86242-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="86242-160">телефонная система с оператором Подключение</span><span class="sxs-lookup"><span data-stu-id="86242-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="86242-161">Операторы Подключение, которые в настоящее время находятся в режиме предварительной версии, если ваш оператор является участником программы Microsoft Operator Подключение, они могут управлять службой для связи через Teams.</span><span class="sxs-lookup"><span data-stu-id="86242-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="86242-162">Ваш оператор связи управляет службами звонков по ЖКХ и пограничными контроллерами сеансов( SBCs), позволяя экономить на приобретении оборудования и управлении им.</span><span class="sxs-lookup"><span data-stu-id="86242-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="86242-163">Оператор Подключение может быть правильным решением для вашей организации, если:</span><span class="sxs-lookup"><span data-stu-id="86242-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="86242-164">План звонков Майкрософт не доступен в вашем географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="86242-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="86242-165">Предпочтительный оператор является участником программы microsoft Operator Подключение.</span><span class="sxs-lookup"><span data-stu-id="86242-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="86242-166">Вы хотите найти нового оператора связи, который сможет звонить в Teams.</span><span class="sxs-lookup"><span data-stu-id="86242-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="86242-167">Сведения о преимуществах и требованиях оператора Подключение, а также список операторов, участвующих в этой программе, см. в [Подключение.](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="86242-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="86242-168">Сведения о настройке оператора Подключение см. в [Подключение.](operator-connect-configure.md)</span><span class="sxs-lookup"><span data-stu-id="86242-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="86242-169">Аспекты конфигурации</span><span class="sxs-lookup"><span data-stu-id="86242-169">Configuration considerations</span></span>

<span data-ttu-id="86242-170">Большинство телефонная система функций одинаковы независимо от того, какой способ подключения вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="86242-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="86242-171">Например, доступны параметры неотвеченных параметров и переадваровки параметров, переадстройки звонка, пользовательской музыки на удержании, в парке вызовов, в общей строке и в голосовых приложениях.</span><span class="sxs-lookup"><span data-stu-id="86242-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="86242-172">Полный список функций телефонная система см. в этой [телефонная система.](here-s-what-you-get-with-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="86242-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="86242-173">Однако существуют некоторые различия в функциональности, которые влияют на настройку телефонная система функций.</span><span class="sxs-lookup"><span data-stu-id="86242-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="86242-174">Например, чтобы настроить маршрутику вызовов, прямая маршрутная маршрутия требует дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="86242-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="86242-175">В качестве еще одного примера прямая маршрутия предоставляет маршрутную маршрутику по расположению (LBR), что позволяет ограничить обход платных номеров в определенных географических расположениях, где это запрещено.</span><span class="sxs-lookup"><span data-stu-id="86242-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="86242-176">Телефон управления номерами</span><span class="sxs-lookup"><span data-stu-id="86242-176">Phone number management</span></span>

<span data-ttu-id="86242-177">У корпорации Майкрософт есть два типа доступных номеров телефонов: номера абонентов (пользователей), которые могут быть назначены пользователям в вашей организации, и номера служб, доступные в качестве платных и бесплатных номеров служб.</span><span class="sxs-lookup"><span data-stu-id="86242-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="86242-178">Номера служб имеют более высокую пропускную способность при одновременном звонке, чем номера абонентов, и могут быть назначены таким службам, как аудиоконференцию, автоотединение или очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="86242-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="86242-179">Вам потребуется принять решение:</span><span class="sxs-lookup"><span data-stu-id="86242-179">You will need to decide:</span></span>

- <span data-ttu-id="86242-180">В каких расположениях нужны новые телефонные номера от Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="86242-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="86242-181">Какой тип номера телефона (абонент или служба) мне нужен?</span><span class="sxs-lookup"><span data-stu-id="86242-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="86242-182">Как сделать так, чтобы существующие номера телефонов были Teams?</span><span class="sxs-lookup"><span data-stu-id="86242-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="86242-183">Способ получения номеров телефонов и управление ими зависит от варианта подключения к ДНР.</span><span class="sxs-lookup"><span data-stu-id="86242-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="86242-184">Сведения об управлении номерами телефонов для плана звонков см. в управлении [номерами телефонов для организации.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="86242-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="86242-185">Сведения об управлении номерами телефонов для прямой маршрутки см. в настройках номера телефона и в том, как включить корпоративную [голосовую и голосовую почту.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)</span><span class="sxs-lookup"><span data-stu-id="86242-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="86242-186">Сведения об управлении номерами телефонов с помощью оператора Подключение см. в этой [Подключение.](operator-connect-configure.md#set-up-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="86242-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="86242-187">Маршрутия вызовов и наборы телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="86242-187">Call routing and dial plans</span></span>

<span data-ttu-id="86242-188">Способ настройки маршрутизов зависит от варианта подключения к STN.</span><span class="sxs-lookup"><span data-stu-id="86242-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="86242-189">Для планов звонков основная часть маршрутизов обрабатывается инфраструктурой плана звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="86242-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="86242-190">Настройте пользовательские наборные планы для перевода номеров для авторизации вызовов и маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="86242-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="86242-191">Дополнительные сведения см. [в теме Что такое планы набора номера?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="86242-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="86242-192">При прямой маршрутике необходимо настроить маршрутику зова, указав голосовые маршруты и назначив пользователям политики маршрутизов голосовой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="86242-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="86242-193">Вы можете настроить планы набора номера для перевода номеров на уровне связи, чтобы обеспечить возможность связи с контроллерами границ сеанса (SBCs).</span><span class="sxs-lookup"><span data-stu-id="86242-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="86242-194">Дополнительные сведения см. [в](direct-routing-voice-routing.md)настройках перенаправки голосовой связи для прямой маршрутии, [](manage-voice-routing-policies.md) Управлении политиками маршрутинга голосовой связи и [Перевод номеров телефонов.](direct-routing-translate-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="86242-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="86242-195">В Подключение операторов большинство маршрутов звонка управляется оператором.</span><span class="sxs-lookup"><span data-stu-id="86242-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="86242-196">Настройте пользовательские наборные планы для перевода номеров для авторизации вызовов и маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="86242-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="86242-197">Дополнительные сведения см. [в теме Что такое планы набора номера?](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="86242-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="86242-198">Location-Based маршруты для прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="86242-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="86242-199">В некоторых странах и регионах обходить оператора ЗВОНКОВ для снижения затрат на междугородние вызовы запрещено.</span><span class="sxs-lookup"><span data-stu-id="86242-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="86242-200">Location-Based Routing (LBR) для прямой маршрутации позволяет ограничить обход платных номеров для Teams пользователей в зависимости от их географического положения.</span><span class="sxs-lookup"><span data-stu-id="86242-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="86242-201">Дополнительные сведения о планировании и настройке LBR см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="86242-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="86242-202">Планирование маршрутизации на основе расположения для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86242-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="86242-203">Настройка параметров сети для маршрутизации на основе расположения</span><span class="sxs-lookup"><span data-stu-id="86242-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="86242-204">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86242-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="86242-205">Пример работы с Contoso: Location-Based маршруты</span><span class="sxs-lookup"><span data-stu-id="86242-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="86242-206">В нем описывается, как вымышленная многоязычная корпорация Contoso Location-Based маршрутизации для своей организации.</span><span class="sxs-lookup"><span data-stu-id="86242-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="86242-207">Экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="86242-207">Emergency calling</span></span>

<span data-ttu-id="86242-208">Способ настройки экстренных вызовов зависит от варианта подключения к ПСС.</span><span class="sxs-lookup"><span data-stu-id="86242-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="86242-209">Для плана звонков каждый пользователь автоматически может звонить на экстренные вызовы и должен иметь зарегистрированный адрес для экстренного вызова, связанный с номером назначенного им телефона.</span><span class="sxs-lookup"><span data-stu-id="86242-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="86242-210">Поддерживаются динамические экстренные вызовы (в зависимости Teams клиента).</span><span class="sxs-lookup"><span data-stu-id="86242-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="86242-211">Для прямой маршрутизации необходимо определить политики экстренных вызовов для пользователей с помощью политики маршрутизации экстренных вызовов Teams (TeamsEmergencyCallRoutingPolicy), чтобы определить номера экстренных служб и их место назначения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="86242-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="86242-212">Зарегистрированные местоположения для экстренного ситуация не поддерживаются для прямых пользователей маршрутов.</span><span class="sxs-lookup"><span data-stu-id="86242-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="86242-213">Для динамических экстренных вызовов требуется дополнительная настройка для маршрутации экстренных вызовов и, возможно, для подключения партнеров.</span><span class="sxs-lookup"><span data-stu-id="86242-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="86242-214">В случае Подключение операторов для каждого пользователя автоматически включена служба экстренных вызовов, и для этого требуется зарегистрированный адрес для экстренного вызова, связанный с номером назначенного им телефона, но его может настроить только партнер оператора.</span><span class="sxs-lookup"><span data-stu-id="86242-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="86242-215">Поддерживаются динамические экстренные вызовы (в зависимости Teams клиента).</span><span class="sxs-lookup"><span data-stu-id="86242-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="86242-216">Дополнительные сведения о понятиях и терминологии экстренных вызовов, а также о настройке экстренных и динамических вызовов экстренных служб см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="86242-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="86242-217">Управление звонками в экстренные службы</span><span class="sxs-lookup"><span data-stu-id="86242-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="86242-218">Планирование и настройка динамических экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="86242-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="86242-219">Управление политиками экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="86242-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="86242-220">Управление политиками маршрутинга экстренных вызовов для прямой маршрутизы</span><span class="sxs-lookup"><span data-stu-id="86242-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="86242-221">Пример: экстренные вызовы в Contoso</span><span class="sxs-lookup"><span data-stu-id="86242-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="86242-222">В этой статье описывается, как вымышленная многоэтапная корпорация Contoso внедряла экстренные вызовы для своей организации.</span><span class="sxs-lookup"><span data-stu-id="86242-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="86242-223">Топология сети для голосовых функций</span><span class="sxs-lookup"><span data-stu-id="86242-223">Network topology for voice features</span></span>

<span data-ttu-id="86242-224">При развертывании динамических экстренных вызовов Location-Based маршрутизов для прямой маршрутии необходимо настроить параметры сети для использования с этими функциями в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86242-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="86242-225">Чтобы узнать, как настроить параметры сети для сетевых регионов, сетевых сайтов, сетевых подсетей и доверенных IP-адресов, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="86242-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="86242-226">Параметры сети для облачных функций голосовой связи в Microsoft Teams — понятия и термины</span><span class="sxs-lookup"><span data-stu-id="86242-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="86242-227">Управление топологией сети для облачных голосовых функций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86242-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



