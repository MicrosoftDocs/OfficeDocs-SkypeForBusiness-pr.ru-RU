---
title: Развертывание облачной системы голосовой связи
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="24bad-103">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="24bad-103">Cloud voice deployment</span></span>

<span data-ttu-id="24bad-104">Microsoft Teams, центр для командной работы и взаимодействия в Office 365, теперь поддерживает аудиоконференции, а также Телефонную систему и Планы звонков, удовлетворяя еще более широкий спектр потребностей бизнеса. Новые возможности позволяют подключать к звонкам и собраниям Microsoft Teams сторонних участников по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="24bad-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="24bad-105">Со временем мы будем обновлять эту страницу по мере выпуска в Microsoft Teams новых функций облачной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="24bad-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="24bad-106">Практическое руководство по развертыванию Аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24bad-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="24bad-107">Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="24bad-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="24bad-108">Ниже указано, что именно вы получаете вместе с [Аудиоконференциями](https://go.microsoft.com/fwlink/?linkid=858992) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="24bad-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="24bad-109">В этом практическом руководстве представлена платформа взаимодействия с клиентом Office 365 FastTrack и входящие в нее три этапа (выработка концепции, внедрение и извлечение выгоды), которые помогут вам в планировании, развертывании и эксплуатации Аудиоконференций с выгодой для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="24bad-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="24bad-110">Документ приводит примеры результатов по каждому действию и обсуждаемому вопросу.</span><span class="sxs-lookup"><span data-stu-id="24bad-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="24bad-111">Примеры находятся внутри выносных элементов "Совет", и вы можете использовать их как шаблоны в собственной работе.</span><span class="sxs-lookup"><span data-stu-id="24bad-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="24bad-112">Вы увидите сообщение "Подлежит добавлению" на месте информации, которую вам нужно указать в рамках процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="24bad-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="24bad-113">Практическое руководство по телефонной системе с планами звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24bad-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="24bad-114">Телефонная система — это компонент Office 365, позволяющий управлять маршрутизацией звонков, политиками и подготовкой пользователей.</span><span class="sxs-lookup"><span data-stu-id="24bad-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="24bad-115">В него входит система управления телефонными звонками, маршрутизация звонков и настройка отдельных звонков.</span><span class="sxs-lookup"><span data-stu-id="24bad-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="24bad-116">Планы звонков Office 365 представляют собой дополнительный компонент для службы телефонной системы, поставляемый с приложениями Teams и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="24bad-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="24bad-117">Планы звонков предоставляют пользователям в вашей организации основной номер телефона и возможность совершать и принимать звонки за пределами организации по телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="24bad-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="24bad-118">Дополнительные сведения см. в разделах [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) (Возможности телефонной системы в Office 365) и [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429) (Общие сведения о планах звонков в Office 365).</span><span class="sxs-lookup"><span data-stu-id="24bad-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="24bad-119">В этом практическом руководстве представлена платформа взаимодействия с клиентом Office 365 FastTrack и входящие в нее три этапа (выработка концепции, внедрение и извлечение выгоды), которые помогут вам в успешном планировании, развертывании и эксплуатации службы телефонной системы с планами звонков.</span><span class="sxs-lookup"><span data-stu-id="24bad-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="24bad-120">Документ приводит примеры результатов по каждому действию и обсуждаемому вопросу.</span><span class="sxs-lookup"><span data-stu-id="24bad-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="24bad-121">Примеры находятся внутри выносных элементов "Совет", и вы можете использовать их как шаблоны в собственной работе.</span><span class="sxs-lookup"><span data-stu-id="24bad-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="24bad-122">Вы увидите сообщение "Подлежит добавлению" на месте информации, которую вам нужно указать в рамках процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="24bad-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>