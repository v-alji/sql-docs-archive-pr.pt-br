---
title: Removendo uma extensão de renderização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574533"
---
# <a name="removing-a-rendering-extension"></a>Removendo uma extensão de renderização
  Para remover uma [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extensão de renderização, basta remover o `Extension` elemento da extensão de renderização do arquivo rsreportserver.config, localizado em **%programfiles%\microsoft SQL Server \ MSRS10_50. \<Instance Name> Pasta \Reporting Services\ReportServer** Se você tiver feito entradas para um Report Designer, bem como um servidor de relatório, remova o `Extension` elemento do [arquivo de configuração RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) também. Após a remoção das informações de configuração, a extensão de renderização não estará mais disponível para o componente.  
  
## <a name="see-also"></a>Consulte Também  
 [Arquivos de configuração do Reporting Services](../../report-server/reporting-services-configuration-files.md)   
 [Implementando uma extensão de renderização](implementing-a-rendering-extension.md)   
 [Visão geral das extensões de renderização](rendering-extensions-overview.md)   
 [Implementando a interface IRenderingExtension](implementing-the-irenderingextension-interface.md)   
 [Considerações sobre segurança para extensões](../security-considerations-for-extensions.md)   
 [Implantando uma extensão de renderização](deploying-a-rendering-extension.md)  
  
  
