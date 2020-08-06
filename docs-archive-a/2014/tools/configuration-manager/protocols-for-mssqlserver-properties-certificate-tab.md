---
title: Protocolos para propriedades MSSQLSERVER (guia Certificado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.computermgr.cert.general.f1
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 776addd6-25f3-4875-9a71-064035787090
author: stevestein
ms.author: sstein
ms.openlocfilehash: 020d33eba7621f877f8622ca89dbd26a071f16a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683853"
---
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a><span data-ttu-id="7a4c5-102">Protocolos para propriedades MSSQLSERVER (guia Certificado)</span><span class="sxs-lookup"><span data-stu-id="7a4c5-102">Protocols for MSSQLSERVER Properties (Certificate Tab)</span></span>
  <span data-ttu-id="7a4c5-103">Use a guia **Certificado** na caixa de diálogo **Protocolos para Propriedades MSSQLSERVER** para selecionar um certificado para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ou para exibir as propriedades de um certificado.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-103">Use the **Certificate** tab on the **Protocols for MSSQLSERVER Properties** dialog box to select a certificate for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or to view the properties of a certificate.</span></span> <span data-ttu-id="7a4c5-104">Todos os campos estarão em branco até que um certificado seja selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-104">All fields are blank until a certificate is selected.</span></span>  
  
 <span data-ttu-id="7a4c5-105">Os certificados são armazenados localmente para os usuários no computador.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-105">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="7a4c5-106">Para carregar um certificado a ser usado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é necessário estar executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager sob a mesma conta de usuário que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a4c5-106">To load a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="7a4c5-107">Cabeçalho de página</span><span class="sxs-lookup"><span data-stu-id="7a4c5-107">Page Header</span></span>  
 <span data-ttu-id="7a4c5-108">**Exibir**</span><span class="sxs-lookup"><span data-stu-id="7a4c5-108">**View**</span></span>  
 <span data-ttu-id="7a4c5-109">Fornece acesso a detalhes adicionais no certificado.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-109">Provides access to additional details on the certificate.</span></span> <span data-ttu-id="7a4c5-110">Não disponível até que um certificado seja selecionado na caixa **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="7a4c5-110">Not available until a certificate is selected in the **Certificate** box.</span></span> <span data-ttu-id="7a4c5-111">Para obter informações adicionais sobre detalhes do certificado, consulte a documentação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-111">For additional information on certificate details, see your [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
 <span data-ttu-id="7a4c5-112">**Limpar**</span><span class="sxs-lookup"><span data-stu-id="7a4c5-112">**Clear**</span></span>  
 <span data-ttu-id="7a4c5-113">Remove a seleção na caixa **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="7a4c5-113">Removes the selection from the **Certificate** box.</span></span>  
  
 <span data-ttu-id="7a4c5-114">**Certificado**</span><span class="sxs-lookup"><span data-stu-id="7a4c5-114">**Certificate**</span></span>  
 <span data-ttu-id="7a4c5-115">Nome do certificado, conforme determinado pelo provedor de segurança.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-115">Name of certificate as determined by security provider.</span></span> <span data-ttu-id="7a4c5-116">Selecione um certificado para ver os detalhes na grade de propriedades.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-116">Select a certificate to see the details in the properties grid.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a4c5-117">Opções</span><span class="sxs-lookup"><span data-stu-id="7a4c5-117">Options</span></span>  
 <span data-ttu-id="7a4c5-118">Data de Validade</span><span class="sxs-lookup"><span data-stu-id="7a4c5-118">Expiration Date</span></span>  
 <span data-ttu-id="7a4c5-119">A data final do período de validade do certificado.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-119">The final date for the period in which the certificate is valid.</span></span>  
  
 <span data-ttu-id="7a4c5-120">Nome amigável</span><span class="sxs-lookup"><span data-stu-id="7a4c5-120">Friendly Name</span></span>  
 <span data-ttu-id="7a4c5-121">Um nome amigável ou comum do indivíduo ou autoridade de certificação para o qual o certificado é emitido.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-121">A friendly or common name for the individual or certification authority to whom the certificate is issued.</span></span>  
  
 <span data-ttu-id="7a4c5-122">Emitido por</span><span class="sxs-lookup"><span data-stu-id="7a4c5-122">Issued By</span></span>  
 <span data-ttu-id="7a4c5-123">Informações relativas à autoridade de certificação que emitiu o certificado.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-123">Information regarding the certification authority that issued the certificate.</span></span>  
  
 <span data-ttu-id="7a4c5-124">Emitido para</span><span class="sxs-lookup"><span data-stu-id="7a4c5-124">Issued To</span></span>  
 <span data-ttu-id="7a4c5-125">Informações relativas ao destinatário do certificado.</span><span class="sxs-lookup"><span data-stu-id="7a4c5-125">Information regarding the recipient of the certificate.</span></span>  
  
  
