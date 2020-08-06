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
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a>Protocolos para propriedades MSSQLSERVER (guia Certificado)
  Use a guia **Certificado** na caixa de diálogo **Protocolos para Propriedades MSSQLSERVER** para selecionar um certificado para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ou para exibir as propriedades de um certificado. Todos os campos estarão em branco até que um certificado seja selecionado.  
  
 Os certificados são armazenados localmente para os usuários no computador. Para carregar um certificado a ser usado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é necessário estar executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager sob a mesma conta de usuário que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="page-header"></a>Cabeçalho de página  
 **Exibir**  
 Fornece acesso a detalhes adicionais no certificado. Não disponível até que um certificado seja selecionado na caixa **Certificado** . Para obter informações adicionais sobre detalhes do certificado, consulte a documentação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.  
  
 **Limpar**  
 Remove a seleção na caixa **Certificado** .  
  
 **Certificado**  
 Nome do certificado, conforme determinado pelo provedor de segurança. Selecione um certificado para ver os detalhes na grade de propriedades.  
  
## <a name="options"></a>Opções  
 Data de Validade  
 A data final do período de validade do certificado.  
  
 Nome amigável  
 Um nome amigável ou comum do indivíduo ou autoridade de certificação para o qual o certificado é emitido.  
  
 Emitido por  
 Informações relativas à autoridade de certificação que emitiu o certificado.  
  
 Emitido para  
 Informações relativas ao destinatário do certificado.  
  
  
