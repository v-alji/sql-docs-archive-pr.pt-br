---
title: Caixa de diálogo informações sobre representação (Assistente de importação de tabela) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679079"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a>Caixa de diálogo de informações de representação (Assistente de Importação de Tabela)
  Use a página **Informações sobre Representação** para especificar as credenciais que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usará para se conectar à fonte de dados. Para obter mais informações sobre como a representação de credenciais, consulte [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).  
  
## <a name="options"></a>Opções  
 **Nome de usuário e senha específicos do Windows**  
 Selecione esta opção para fazer com que o modelo tabular use as credenciais de segurança de uma conta de usuário do Windows especificada.  
  
 **Nome de usuário**  
 Digite o domínio e o nome da conta de usuário a serem usados. Use o seguinte formato:  
  
 *\<Domain name>* **\\** *\<User account name>*  
  
 Essa opção estará habilitada apenas se a opção **Usar um nome e uma senha específicos** estiver selecionada.  
  
 **Senha**  
 Digite a senha da conta de usuário a ser usada pelo objeto do modelo tabular.  
  
 Essa opção estará habilitada apenas se a opção **Usar um nome e uma senha específicos** estiver selecionada.  
  
 **Conta de serviço**  
 Selecione esta opção para usar as credenciais de segurança associadas ao serviço [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que gerencia o modelo.  
  
## <a name="see-also"></a>Consulte Também  
 [Representação &#40;SSAS tabular&#41;](tabular-models/impersonation-ssas-tabular.md)  
  
  
