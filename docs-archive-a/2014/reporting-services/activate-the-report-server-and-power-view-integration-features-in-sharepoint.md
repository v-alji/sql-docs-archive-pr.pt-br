---
title: Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582330"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a>Ativar o servidor de relatório e os recursos de integração do Power View no SharePoint
  Os [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] recursos do conjunto de sites geralmente são ativados por padrão depois que você instala o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] suplemento para produtos do SharePoint. Em algumas situações, você precisará ativar manualmente os recursos.  
  
 Se você instalar o suplemento do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para Produtos SharePoint 2010 depois da instalação do produto SharePoint, o recurso de integração de Servidor de relatório e o recurso de integração do Power View só será ativado para coleções de sites de raiz. Para outras coleções de sites, você precisará ativar manualmente os recursos. Por exemplo se você tiver uma coleção de sites de **http://[nome do meu servidor]/sites/[nome da coleção de sites]** , será necessário ativar manualmente os recursos da coleção de sites do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .  
  
 Quando não houver nenhuma coleção de sites raiz, o suplemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] registrará em log uma mensagem semelhante à seguinte.  
  
 "O aplicativo Web SharePoint 80 não tem a coleção de sites raiz"  
  
 A mensagem será encontrada no log de instalação do suplemento, chamado "RS_SP_ #. log", em que # é um número de incremento. O arquivo de log será encontrado na pasta Temp Users atual, por exemplo, C:\Users \\ [nome de usuário] \AppData\Local\Temp. Para obter mais informações sobre opções de log com o suplemento, consulte [instalar ou desinstalar o suplemento Reporting Services para sharepoint &#40;sharepoint 2010 e sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).  
  
 Neste tópico:  
  
-   [Para ativar o Servidor de Relatório e os recursos de coleção de sites do Power View:](#bkmk_features)  
  
-   [Para ativar ou desativar o recurso de coleção de sites da Administração Central do Reporting Services:](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a>Para ativar o servidor de relatório e Power View os recursos do conjunto de sites de integração:  
  
1.  Abra seu navegador no site em que você deseja que os recursos do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] estejam ativos.  
  
2.  Clique em **Ações do Site**.  
  
3.  Clique em **Configurações de Site**.  
  
4.  Clique em **Recursos do Conjunto de Sites** no Grupo Administração do Conjunto de Sites.  
  
5.  Localize **Recurso de Integração do Servidor de Relatório** ou **Recurso de Integração do Power View** na lista.  
  
6.  Clique em **Ativar**.  
  
 Para desativar os recursos, é possível usar o mesmo procedimento, mas clique em **Desativar** em vez de **Ativar**.  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a>Para ativar ou desativar Reporting Services recurso de conjunto de sites de administração central:  
  
1.  Abra seu navegador na Administração Central do SharePoint.  
  
2.  Clique em **Ações do Site**.  
  
3.  Clique em **Configurações de Site**.  
  
4.  Clique em **Recursos do Conjunto de Sites** no Grupo Administração do Conjunto de Sites.  
  
5.  Localize **Recurso da Administração Central do Servidor de Relatório** na lista.  
  
6.  Clique em **Ativar**.  
  
 Para desativar o recurso, é possível usar o mesmo procedimento, mas clique em **Desativar** em vez de **Ativar**.  
  
## <a name="next-steps"></a>Próximas etapas  
 Depois que o recurso for ativado, será possível continuar com a integração do servidor.  
  
## <a name="see-also"></a>Consulte Também  
 [Instalar ou desinstalar o suplemento Reporting Services para SharePoint &#40;SharePoint 2010 e SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
