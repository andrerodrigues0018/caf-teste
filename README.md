# caf-teste
adf

1. Plugin duplicado
O '@caf.io/react-native-sdk' está aparecendo duas vezes no array de plugins. Deixa só uma entrada (a que tem a config) e remove a linha solta de cima.

2. Config do PayFace
O PayFace precisa do 'iproov-lite' junto, os dois usam Protobuf JavaLite, e o PayFace sozinho quebra o build. Como você vai usar só liveness, fica assim:

plugins: [
  // seus outros plugins
  [
    '@caf.io/react-native-sdk',
    {
      faceLiveness: true,
      faceLivenessUI: true,
      documentDetector: false,
      documentDetectorUI: false,
      livenessProviders: ['payface', 'iproov-lite'],
    },
  ],
]