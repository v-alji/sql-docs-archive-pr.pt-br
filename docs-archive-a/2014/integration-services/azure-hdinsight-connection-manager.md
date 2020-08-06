---
title: Gerenciador de Conexões do Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPHDICM.F1
- SQL11.DTS.DESIGNER.AFPHDICM.F1
ms.assetid: 850a978d-5dba-45b6-a10e-306aafbc353d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaf2f57fec50a58ad1b7e7578407fb6cf3fa0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678941"
---
# <a name="azure-hdinsight-connection-manager"></a>Gerenciador de Conexões do Azure HDInsight
O **Gerenciador de Conexões do Azure HDInsight** permite que um pacote do SSIS se conecte a um cluster HDInsight do Azure.

Para criar e configurar um **Gerenciador de Conexões do Azure HDInsight**, siga as etapas abaixo:

1. Na caixa de diálogo **Adicionar Gerenciador de Conexões do SSIS**, selecione **AzureHDInsight** e clique em **Adicionar**.
2. Na caixa de diálogo **Editor do Gerenciador de Conexões do Azure HDInsight**, especifique o **Nome DNS de Cluster** (sem o prefixo de protocolo), **Nome de usuário** e **Senha** para o cluster HDInsight ao qual se conectar.
3. Clique em **OK** para fechar a caixa de diálogo.
4. Você pode ver as propriedades do gerenciador de conexões criado na janela **Propriedades** .
