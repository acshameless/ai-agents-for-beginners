<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c692a8975d7d5b99575a553de1c5e8a7",
  "translation_date": "2025-07-12T11:05:00+00:00",
  "source_file": "08-multi-agent/README.md",
  "language_code": "pa"
}
-->
[![Multi-Agent Design](../../../translated_images/lesson-8-thumbnail.278a3e4a59137d625df92de3f885d2da2a92b1f7017abba25a99fb25edd83a55.pa.png)](https://youtu.be/V6HpE9hZEx0?si=A7K44uMCqgvLQVCa)

> _(ਇਸ ਪਾਠ ਦਾ ਵੀਡੀਓ ਦੇਖਣ ਲਈ ਉਪਰ ਦਿੱਤੀ ਤਸਵੀਰ 'ਤੇ ਕਲਿੱਕ ਕਰੋ)_

# ਮਲਟੀ-ਏਜੰਟ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ

ਜਿਵੇਂ ਹੀ ਤੁਸੀਂ ਕਿਸੇ ਪ੍ਰੋਜੈਕਟ 'ਤੇ ਕੰਮ ਕਰਨਾ ਸ਼ੁਰੂ ਕਰਦੇ ਹੋ ਜਿਸ ਵਿੱਚ ਕਈ ਏਜੰਟ ਸ਼ਾਮਲ ਹੁੰਦੇ ਹਨ, ਤੁਹਾਨੂੰ ਮਲਟੀ-ਏਜੰਟ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ ਬਾਰੇ ਸੋਚਣਾ ਪਵੇਗਾ। ਪਰ ਇਹ ਸਪਸ਼ਟ ਨਹੀਂ ਹੁੰਦਾ ਕਿ ਕਦੋਂ ਮਲਟੀ-ਏਜੰਟ ਵਰਤਣੇ ਹਨ ਅਤੇ ਇਸਦੇ ਫਾਇਦੇ ਕੀ ਹਨ।

## ਪਰਿਚਯ

ਇਸ ਪਾਠ ਵਿੱਚ ਅਸੀਂ ਹੇਠਾਂ ਦਿੱਤੇ ਸਵਾਲਾਂ ਦੇ ਜਵਾਬ ਲੱਭਣ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰਾਂਗੇ:

- ਕਿਹੜੇ ਸਥਿਤੀਆਂ ਵਿੱਚ ਮਲਟੀ-ਏਜੰਟ ਲਾਗੂ ਹੁੰਦੇ ਹਨ?
- ਇੱਕ ਹੀ ਏਜੰਟ ਦੇ ਬਜਾਏ ਮਲਟੀ-ਏਜੰਟ ਵਰਤਣ ਦੇ ਕੀ ਫਾਇਦੇ ਹਨ?
- ਮਲਟੀ-ਏਜੰਟ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ ਨੂੰ ਲਾਗੂ ਕਰਨ ਦੇ ਮੁੱਖ ਹਿੱਸੇ ਕੀ ਹਨ?
- ਅਸੀਂ ਕਿਵੇਂ ਦੇਖ ਸਕਦੇ ਹਾਂ ਕਿ ਕਈ ਏਜੰਟ ਇਕ ਦੂਜੇ ਨਾਲ ਕਿਵੇਂ ਇੰਟਰੈਕਟ ਕਰ ਰਹੇ ਹਨ?

## ਸਿੱਖਣ ਦੇ ਲਕੜ

ਇਸ ਪਾਠ ਤੋਂ ਬਾਅਦ, ਤੁਸੀਂ ਸਮਰੱਥ ਹੋਵੋਗੇ:

- ਉਹ ਸਥਿਤੀਆਂ ਪਛਾਣਨ ਦੀ ਜਿੱਥੇ ਮਲਟੀ-ਏਜੰਟ ਲਾਗੂ ਹੁੰਦੇ ਹਨ
- ਮਲਟੀ-ਏਜੰਟ ਵਰਤਣ ਦੇ ਫਾਇਦੇ ਸਮਝਣ ਦੀ
- ਮਲਟੀ-ਏਜੰਟ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ ਦੇ ਮੁੱਖ ਹਿੱਸਿਆਂ ਨੂੰ ਸਮਝਣ ਦੀ

ਵੱਡੀ ਤਸਵੀਰ ਕੀ ਹੈ?

*ਮਲਟੀ-ਏਜੰਟ ਇੱਕ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ ਹੈ ਜੋ ਕਈ ਏਜੰਟਾਂ ਨੂੰ ਮਿਲ ਕੇ ਇੱਕ ਸਾਂਝਾ ਮਕਸਦ ਹਾਸਲ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ।*

ਇਹ ਪੈਟਰਨ ਵੱਖ-ਵੱਖ ਖੇਤਰਾਂ ਵਿੱਚ ਵਰਤਿਆ ਜਾਂਦਾ ਹੈ, ਜਿਵੇਂ ਕਿ ਰੋਬੋਟਿਕਸ, ਸਵੈਚਾਲਿਤ ਪ੍ਰਣਾਲੀਆਂ ਅਤੇ ਵੰਡੇ ਹੋਏ ਕੰਪਿਊਟਿੰਗ ਵਿੱਚ।

## ਉਹ ਸਥਿਤੀਆਂ ਜਿੱਥੇ ਮਲਟੀ-ਏਜੰਟ ਲਾਗੂ ਹੁੰਦੇ ਹਨ

ਤਾਂ ਮਲਟੀ-ਏਜੰਟ ਵਰਤਣ ਲਈ ਕਿਹੜੀਆਂ ਸਥਿਤੀਆਂ ਵਧੀਆ ਹਨ? ਜਵਾਬ ਇਹ ਹੈ ਕਿ ਕਈ ਸਥਿਤੀਆਂ ਹਨ ਜਿੱਥੇ ਕਈ ਏਜੰਟ ਵਰਤਣਾ ਲਾਭਦਾਇਕ ਹੁੰਦਾ ਹੈ, ਖਾਸ ਕਰਕੇ ਹੇਠਾਂ ਦਿੱਤੇ ਮਾਮਲਿਆਂ ਵਿੱਚ:

- **ਵੱਡਾ ਕੰਮ ਦਾ ਬੋਝ**: ਵੱਡੇ ਕੰਮ ਨੂੰ ਛੋਟੇ-ਛੋਟੇ ਹਿੱਸਿਆਂ ਵਿੱਚ ਵੰਡਿਆ ਜਾ ਸਕਦਾ ਹੈ ਅਤੇ ਵੱਖ-ਵੱਖ ਏਜੰਟਾਂ ਨੂੰ ਦਿੱਤਾ ਜਾ ਸਕਦਾ ਹੈ, ਜਿਸ ਨਾਲ ਸਮਾਂ ਬਚਦਾ ਹੈ ਅਤੇ ਕੰਮ ਤੇਜ਼ੀ ਨਾਲ ਮੁਕੰਮਲ ਹੁੰਦਾ ਹੈ। ਉਦਾਹਰਨ ਵਜੋਂ ਵੱਡੇ ਡਾਟਾ ਪ੍ਰੋਸੈਸਿੰਗ ਕੰਮ ਨੂੰ ਲਿਆ ਜਾ ਸਕਦਾ ਹੈ।
- **ਜਟਿਲ ਕੰਮ**: ਜਟਿਲ ਕੰਮਾਂ ਨੂੰ ਵੀ ਛੋਟੇ ਹਿੱਸਿਆਂ ਵਿੱਚ ਵੰਡਿਆ ਜਾ ਸਕਦਾ ਹੈ ਅਤੇ ਵੱਖ-ਵੱਖ ਏਜੰਟਾਂ ਨੂੰ ਦਿੱਤਾ ਜਾ ਸਕਦਾ ਹੈ, ਜਿਹੜੇ ਹਰ ਇੱਕ ਕੰਮ ਦੇ ਖਾਸ ਪੱਖ ਨੂੰ ਸੰਭਾਲਦੇ ਹਨ। ਉਦਾਹਰਨ ਵਜੋਂ ਸਵੈਚਾਲਿਤ ਵਾਹਨਾਂ ਵਿੱਚ ਵੱਖ-ਵੱਖ ਏਜੰਟ ਨੈਵੀਗੇਸ਼ਨ, ਰੁਕਾਵਟ ਪਛਾਣ ਅਤੇ ਹੋਰ ਵਾਹਨਾਂ ਨਾਲ ਸੰਚਾਰ ਸੰਭਾਲਦੇ ਹਨ।
- **ਵੱਖ-ਵੱਖ ਮਾਹਿਰਤਾ**: ਵੱਖ-ਵੱਖ ਏਜੰਟਾਂ ਕੋਲ ਵੱਖ-ਵੱਖ ਮਾਹਿਰਤਾ ਹੋ ਸਕਦੀ ਹੈ, ਜਿਸ ਨਾਲ ਉਹ ਇੱਕ ਹੀ ਏਜੰਟ ਨਾਲੋਂ ਵੱਧ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਢੰਗ ਨਾਲ ਕੰਮ ਦੇ ਵੱਖ-ਵੱਖ ਪੱਖਾਂ ਨੂੰ ਸੰਭਾਲ ਸਕਦੇ ਹਨ। ਉਦਾਹਰਨ ਵਜੋਂ ਸਿਹਤ ਸੇਵਾ ਵਿੱਚ, ਜਿੱਥੇ ਏਜੰਟ ਡਾਇਗਨੋਸਟਿਕਸ, ਇਲਾਜ ਯੋਜਨਾਵਾਂ ਅਤੇ ਮਰੀਜ਼ ਦੀ ਨਿਗਰਾਨੀ ਕਰਦੇ ਹਨ।

## ਇੱਕ ਏਜੰਟ ਦੇ ਬਜਾਏ ਮਲਟੀ-ਏਜੰਟ ਵਰਤਣ ਦੇ ਫਾਇਦੇ

ਸਧਾਰਨ ਕੰਮਾਂ ਲਈ ਇੱਕ ਏਜੰਟ ਸਿਸਟਮ ਚੰਗਾ ਕੰਮ ਕਰ ਸਕਦਾ ਹੈ, ਪਰ ਜਟਿਲ ਕੰਮਾਂ ਲਈ ਕਈ ਏਜੰਟ ਵਰਤਣ ਨਾਲ ਕਈ ਫਾਇਦੇ ਹੁੰਦੇ ਹਨ:

- **ਮਾਹਿਰਤਾ**: ਹਰ ਏਜੰਟ ਕਿਸੇ ਖਾਸ ਕੰਮ ਵਿੱਚ ਮਾਹਿਰ ਹੋ ਸਕਦਾ ਹੈ। ਇੱਕ ਹੀ ਏਜੰਟ ਵਿੱਚ ਮਾਹਿਰਤਾ ਦੀ ਘਾਟ ਹੁੰਦੀ ਹੈ, ਜਿਸ ਨਾਲ ਉਹ ਜਟਿਲ ਕੰਮਾਂ ਵਿੱਚ ਗਲਤ ਕੰਮ ਕਰ ਸਕਦਾ ਹੈ ਜਾਂ ਗੁੰਝਲਦਾਰ ਹੋ ਸਕਦਾ ਹੈ।
- **ਵਧਾਉਣਯੋਗਤਾ**: ਸਿਸਟਮ ਨੂੰ ਵਧਾਉਣਾ ਅਸਾਨ ਹੁੰਦਾ ਹੈ ਜਦੋਂ ਤੁਸੀਂ ਹੋਰ ਏਜੰਟ ਸ਼ਾਮਲ ਕਰਦੇ ਹੋ, ਨਾ ਕਿ ਇੱਕ ਹੀ ਏਜੰਟ 'ਤੇ ਬੋਝ ਵਧਾਉਂਦੇ ਹੋ।
- **ਫਾਲਟ ਟੋਲਰੈਂਸ**: ਜੇ ਇੱਕ ਏਜੰਟ ਫੇਲ ਹੋ ਜਾਂਦਾ ਹੈ, ਤਾਂ ਹੋਰ ਏਜੰਟ ਕੰਮ ਜਾਰੀ ਰੱਖ ਸਕਦੇ ਹਨ, ਜਿਸ ਨਾਲ ਸਿਸਟਮ ਦੀ ਭਰੋਸੇਯੋਗਤਾ ਬਣੀ ਰਹਿੰਦੀ ਹੈ।

ਆਓ ਇੱਕ ਉਦਾਹਰਨ ਲਵਾਂ, ਇੱਕ ਯੂਜ਼ਰ ਲਈ ਯਾਤਰਾ ਬੁਕ ਕਰਨੀ ਹੈ। ਇੱਕ ਏਜੰਟ ਸਿਸਟਮ ਨੂੰ ਯਾਤਰਾ ਬੁਕਿੰਗ ਦੇ ਸਾਰੇ ਪੱਖ ਸੰਭਾਲਣੇ ਪੈਣਗੇ, ਜਿਵੇਂ ਕਿ ਫਲਾਈਟ ਲੱਭਣਾ, ਹੋਟਲ ਬੁਕ ਕਰਨਾ ਅਤੇ ਕਾਰ ਕਿਰਾਏ 'ਤੇ ਲੈਣਾ। ਇਹ ਇੱਕ ਜਟਿਲ ਅਤੇ ਇਕਠਾ ਸਿਸਟਮ ਬਣ ਸਕਦਾ ਹੈ ਜੋ ਸੰਭਾਲਣਾ ਅਤੇ ਵਧਾਉਣਾ ਮੁਸ਼ਕਲ ਹੁੰਦਾ ਹੈ। ਦੂਜੇ ਪਾਸੇ, ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮ ਵਿੱਚ ਵੱਖ-ਵੱਖ ਏਜੰਟ ਫਲਾਈਟ ਲੱਭਣ, ਹੋਟਲ ਬੁਕ ਕਰਨ ਅਤੇ ਕਾਰ ਕਿਰਾਏ 'ਤੇ ਲੈਣ ਵਿੱਚ ਮਾਹਿਰ ਹੋਣਗੇ। ਇਸ ਨਾਲ ਸਿਸਟਮ ਜ਼ਿਆਦਾ ਮੋਡੀਊਲਰ, ਆਸਾਨ ਅਤੇ ਵਧਾਉਣਯੋਗ ਬਣ ਜਾਂਦਾ ਹੈ।

ਇਸਨੂੰ ਤੁਲਨਾ ਕਰੋ ਇੱਕ ਮੋਮ-ਐਂਡ-ਪੌਪ ਸਟੋਰ ਵੱਲੋਂ ਚਲਾਏ ਜਾਣ ਵਾਲੇ ਟ੍ਰੈਵਲ ਬਿਊਰੋ ਨਾਲ, ਜੋ ਸਾਰੇ ਕੰਮ ਇੱਕ ਏਜੰਟ ਕਰਦਾ ਹੈ, ਅਤੇ ਇੱਕ ਫ੍ਰੈਂਚਾਈਜ਼ ਵੱਲੋਂ ਚਲਾਏ ਜਾਣ ਵਾਲੇ ਟ੍ਰੈਵਲ ਬਿਊਰੋ ਨਾਲ, ਜਿੱਥੇ ਵੱਖ-ਵੱਖ ਏਜੰਟ ਵੱਖ-ਵੱਖ ਕੰਮ ਕਰਦੇ ਹਨ।

## ਮਲਟੀ-ਏਜੰਟ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ ਲਾਗੂ ਕਰਨ ਦੇ ਮੁੱਖ ਹਿੱਸੇ

ਮਲਟੀ-ਏਜੰਟ ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ ਲਾਗੂ ਕਰਨ ਤੋਂ ਪਹਿਲਾਂ, ਤੁਹਾਨੂੰ ਪੈਟਰਨ ਦੇ ਮੁੱਖ ਹਿੱਸਿਆਂ ਨੂੰ ਸਮਝਣਾ ਜਰੂਰੀ ਹੈ।

ਆਓ ਫਿਰ ਤੋਂ ਯੂਜ਼ਰ ਲਈ ਯਾਤਰਾ ਬੁਕ ਕਰਨ ਦੀ ਉਦਾਹਰਨ ਲਵਾਂ। ਇਸ ਮਾਮਲੇ ਵਿੱਚ, ਮੁੱਖ ਹਿੱਸੇ ਸ਼ਾਮਲ ਹੋਣਗੇ:

- **ਏਜੰਟ ਸੰਚਾਰ**: ਫਲਾਈਟ ਲੱਭਣ, ਹੋਟਲ ਬੁਕ ਕਰਨ ਅਤੇ ਕਾਰ ਕਿਰਾਏ 'ਤੇ ਲੈਣ ਵਾਲੇ ਏਜੰਟਾਂ ਨੂੰ ਯੂਜ਼ਰ ਦੀਆਂ ਪਸੰਦਾਂ ਅਤੇ ਸੀਮਾਵਾਂ ਬਾਰੇ ਜਾਣਕਾਰੀ ਸਾਂਝੀ ਕਰਨੀ ਪੈਂਦੀ ਹੈ। ਤੁਹਾਨੂੰ ਇਹ ਫੈਸਲਾ ਕਰਨਾ ਪਵੇਗਾ ਕਿ ਇਹ ਸੰਚਾਰ ਕਿਹੜੇ ਪ੍ਰੋਟੋਕੋਲ ਅਤੇ ਤਰੀਕਿਆਂ ਨਾਲ ਹੋਵੇਗਾ। ਉਦਾਹਰਨ ਵਜੋਂ, ਫਲਾਈਟ ਲੱਭਣ ਵਾਲਾ ਏਜੰਟ ਹੋਟਲ ਬੁਕ ਕਰਨ ਵਾਲੇ ਏਜੰਟ ਨਾਲ ਗੱਲ ਕਰੇ ਤਾਂ ਕਿ ਹੋਟਲ ਫਲਾਈਟ ਦੀਆਂ ਤਰੀਖਾਂ ਨਾਲ ਮੇਲ ਖਾਂਦਾ ਹੋਵੇ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਏਜੰਟਾਂ ਨੂੰ ਯੂਜ਼ਰ ਦੀ ਯਾਤਰਾ ਦੀਆਂ ਤਰੀਖਾਂ ਬਾਰੇ ਜਾਣਕਾਰੀ ਸਾਂਝੀ ਕਰਨੀ ਪਵੇਗੀ, ਅਤੇ ਤੁਹਾਨੂੰ ਇਹ ਫੈਸਲਾ ਕਰਨਾ ਪਵੇਗਾ ਕਿ *ਕਿਹੜੇ ਏਜੰਟ ਜਾਣਕਾਰੀ ਸਾਂਝੀ ਕਰ ਰਹੇ ਹਨ ਅਤੇ ਕਿਵੇਂ ਕਰ ਰਹੇ ਹਨ*।
- **ਸਮਨਵਯ ਮਕੈਨਿਜ਼ਮ**: ਏਜੰਟਾਂ ਨੂੰ ਆਪਣੇ ਕੰਮਾਂ ਨੂੰ ਇਸ ਤਰ੍ਹਾਂ ਸਮਨਵਯਿਤ ਕਰਨਾ ਪਵੇਗਾ ਕਿ ਯੂਜ਼ਰ ਦੀਆਂ ਪਸੰਦਾਂ ਅਤੇ ਸੀਮਾਵਾਂ ਪੂਰੀਆਂ ਹੋਣ। ਉਦਾਹਰਨ ਵਜੋਂ, ਯੂਜ਼ਰ ਚਾਹੁੰਦਾ ਹੈ ਕਿ ਹੋਟਲ ਹਵਾਈ ਅੱਡੇ ਦੇ ਨੇੜੇ ਹੋਵੇ, ਪਰ ਕਾਰ ਕਿਰਾਏ 'ਤੇ ਸਿਰਫ ਹਵਾਈ ਅੱਡੇ 'ਤੇ ਮਿਲਦੀ ਹੈ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਹੋਟਲ ਬੁਕ ਕਰਨ ਵਾਲਾ ਏਜੰਟ ਕਾਰ ਕਿਰਾਏ ਵਾਲੇ ਏਜੰਟ ਨਾਲ ਗੱਲ ਕਰੇ ਤਾਂ ਜੋ ਯੂਜ਼ਰ ਦੀਆਂ ਪਸੰਦਾਂ ਅਤੇ ਸੀਮਾਵਾਂ ਪੂਰੀਆਂ ਹੋਣ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਤੁਹਾਨੂੰ ਇਹ ਫੈਸਲਾ ਕਰਨਾ ਪਵੇਗਾ ਕਿ *ਏਜੰਟ ਆਪਣੇ ਕੰਮ ਕਿਵੇਂ ਸਮਨਵਯਿਤ ਕਰ ਰਹੇ ਹਨ*।
- **ਏਜੰਟ ਆਰਕੀਟੈਕਚਰ**: ਏਜੰਟਾਂ ਕੋਲ ਅੰਦਰੂਨੀ ਢਾਂਚਾ ਹੋਣਾ ਚਾਹੀਦਾ ਹੈ ਜੋ ਫੈਸਲੇ ਕਰਨ ਅਤੇ ਯੂਜ਼ਰ ਨਾਲ ਇੰਟਰੈਕਸ਼ਨ ਤੋਂ ਸਿੱਖਣ ਵਿੱਚ ਸਹਾਇਕ ਹੋਵੇ। ਉਦਾਹਰਨ ਵਜੋਂ, ਫਲਾਈਟ ਲੱਭਣ ਵਾਲਾ ਏਜੰਟ ਇਹ ਫੈਸਲਾ ਕਰੇ ਕਿ ਕਿਹੜੀਆਂ ਫਲਾਈਟਾਂ ਯੂਜ਼ਰ ਨੂੰ ਸੁਝਾਈਆਂ ਜਾਣ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਤੁਹਾਨੂੰ ਇਹ ਫੈਸਲਾ ਕਰਨਾ ਪਵੇਗਾ ਕਿ *ਏਜੰਟ ਕਿਵੇਂ ਫੈਸਲੇ ਕਰ ਰਹੇ ਹਨ ਅਤੇ ਯੂਜ਼ਰ ਨਾਲ ਇੰਟਰੈਕਸ਼ਨ ਤੋਂ ਸਿੱਖ ਰਹੇ ਹਨ*। ਉਦਾਹਰਨ ਵਜੋਂ, ਫਲਾਈਟ ਲੱਭਣ ਵਾਲਾ ਏਜੰਟ ਮਸ਼ੀਨ ਲਰਨਿੰਗ ਮਾਡਲ ਵਰਤ ਸਕਦਾ ਹੈ ਜੋ ਪਿਛਲੇ ਪਸੰਦਾਂ ਦੇ ਆਧਾਰ 'ਤੇ ਫਲਾਈਟਾਂ ਦੀ ਸਿਫਾਰਸ਼ ਕਰਦਾ ਹੈ।
- **ਮਲਟੀ-ਏਜੰਟ ਇੰਟਰੈਕਸ਼ਨ ਵਿੱਚ ਦਿੱਖ**: ਤੁਹਾਨੂੰ ਇਹ ਵੇਖਣ ਦੀ ਜ਼ਰੂਰਤ ਹੈ ਕਿ ਕਈ ਏਜੰਟ ਇਕ ਦੂਜੇ ਨਾਲ ਕਿਵੇਂ ਇੰਟਰੈਕਟ ਕਰ ਰਹੇ ਹਨ। ਇਸ ਲਈ ਤੁਹਾਨੂੰ ਟੂਲ ਅਤੇ ਤਕਨੀਕਾਂ ਦੀ ਲੋੜ ਹੈ ਜੋ ਏਜੰਟਾਂ ਦੀਆਂ ਗਤੀਵਿਧੀਆਂ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨਾਂ ਨੂੰ ਟਰੈਕ ਕਰ ਸਕਣ। ਇਹ ਲੌਗਿੰਗ ਅਤੇ ਮਾਨੀਟਰਿੰਗ ਟੂਲ, ਵਿਜ਼ੂਅਲਾਈਜ਼ੇਸ਼ਨ ਟੂਲ ਅਤੇ ਪ੍ਰਦਰਸ਼ਨ ਮੈਟਰਿਕਸ ਦੇ ਰੂਪ ਵਿੱਚ ਹੋ ਸਕਦਾ ਹੈ।
- **ਮਲਟੀ-ਏਜੰਟ ਪੈਟਰਨ**: ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮ ਲਾਗੂ ਕਰਨ ਲਈ ਵੱਖ-ਵੱਖ ਪੈਟਰਨ ਹੁੰਦੇ ਹਨ, ਜਿਵੇਂ ਕਿ ਕੇਂਦਰੀਕ੍ਰਿਤ, ਵਿਤਰਿਤ ਅਤੇ ਹਾਈਬ੍ਰਿਡ ਆਰਕੀਟੈਕਚਰ। ਤੁਹਾਨੂੰ ਆਪਣੇ ਕੇਸ ਲਈ ਸਭ ਤੋਂ ਵਧੀਆ ਪੈਟਰਨ ਚੁਣਨਾ ਪਵੇਗਾ।
- **ਹਿਊਮਨ ਇਨ ਦ ਲੂਪ**: ਜ਼ਿਆਦਾਤਰ ਮਾਮਲਿਆਂ ਵਿੱਚ, ਤੁਹਾਡੇ ਕੋਲ ਹਿਊਮਨ ਇਨ ਦ ਲੂਪ ਹੁੰਦਾ ਹੈ ਅਤੇ ਤੁਹਾਨੂੰ ਏਜੰਟਾਂ ਨੂੰ ਦੱਸਣਾ ਪੈਂਦਾ ਹੈ ਕਿ ਕਦੋਂ ਮਨੁੱਖੀ ਦਖਲਅੰਦਾਜ਼ੀ ਲਈ ਪੁੱਛਣਾ ਹੈ। ਉਦਾਹਰਨ ਵਜੋਂ, ਜਦੋਂ ਯੂਜ਼ਰ ਕਿਸੇ ਖਾਸ ਹੋਟਲ ਜਾਂ ਫਲਾਈਟ ਲਈ ਪੁੱਛਦਾ ਹੈ ਜੋ ਏਜੰਟਾਂ ਨੇ ਸਿਫਾਰਸ਼ ਨਹੀਂ ਕੀਤੀ ਜਾਂ ਬੁਕਿੰਗ ਤੋਂ ਪਹਿਲਾਂ ਪੁਸ਼ਟੀ ਮੰਗਦਾ ਹੈ।

## ਮਲਟੀ-ਏਜੰਟ ਇੰਟਰੈਕਸ਼ਨ ਵਿੱਚ ਦਿੱਖ

ਇਹ ਜਰੂਰੀ ਹੈ ਕਿ ਤੁਸੀਂ ਵੇਖ ਸਕੋ ਕਿ ਕਈ ਏਜੰਟ ਇਕ ਦੂਜੇ ਨਾਲ ਕਿਵੇਂ ਇੰਟਰੈਕਟ ਕਰ ਰਹੇ ਹਨ। ਇਹ ਦਿੱਖ ਡਿਬੱਗਿੰਗ, ਅਪਟੀਮਾਈਜ਼ੇਸ਼ਨ ਅਤੇ ਸਿਸਟਮ ਦੀ ਕੁੱਲ ਪ੍ਰਭਾਵਸ਼ੀਲਤਾ ਲਈ ਬਹੁਤ ਜਰੂਰੀ ਹੈ। ਇਸ ਲਈ ਤੁਹਾਨੂੰ ਟੂਲ ਅਤੇ ਤਕਨੀਕਾਂ ਦੀ ਲੋੜ ਹੈ ਜੋ ਏਜੰਟਾਂ ਦੀਆਂ ਗਤੀਵਿਧੀਆਂ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨਾਂ ਨੂੰ ਟਰੈਕ ਕਰ ਸਕਣ। ਇਹ ਲੌਗਿੰਗ ਅਤੇ ਮਾਨੀਟਰਿੰਗ ਟੂਲ, ਵਿਜ਼ੂਅਲਾਈਜ਼ੇਸ਼ਨ ਟੂਲ ਅਤੇ ਪ੍ਰਦਰਸ਼ਨ ਮੈਟਰਿਕਸ ਦੇ ਰੂਪ ਵਿੱਚ ਹੋ ਸਕਦਾ ਹੈ।

ਉਦਾਹਰਨ ਵਜੋਂ, ਯੂਜ਼ਰ ਲਈ ਯਾਤਰਾ ਬੁਕ ਕਰਨ ਦੇ ਮਾਮਲੇ ਵਿੱਚ, ਤੁਸੀਂ ਇੱਕ ਡੈਸ਼ਬੋਰਡ ਰੱਖ ਸਕਦੇ ਹੋ ਜੋ ਹਰ ਏਜੰਟ ਦੀ ਸਥਿਤੀ, ਯੂਜ਼ਰ ਦੀਆਂ ਪਸੰਦਾਂ ਅਤੇ ਸੀਮਾਵਾਂ, ਅਤੇ ਏਜੰਟਾਂ ਵਿਚਕਾਰ ਇੰਟਰੈਕਸ਼ਨਾਂ ਨੂੰ ਦਿਖਾਉਂਦਾ ਹੈ। ਇਹ ਡੈਸ਼ਬੋਰਡ ਯੂਜ਼ਰ ਦੀਆਂ ਯਾਤਰਾ ਦੀਆਂ ਤਰੀਖਾਂ, ਫਲਾਈਟ ਏਜੰਟ ਵੱਲੋਂ ਸੁਝਾਈਆਂ ਫਲਾਈਟਾਂ, ਹੋਟਲ ਏਜੰਟ ਵੱਲੋਂ ਸੁਝਾਏ ਹੋਟਲ ਅਤੇ ਕਾਰ ਕਿਰਾਏ ਵਾਲੇ ਏਜੰਟ ਵੱਲੋਂ ਸੁਝਾਏ ਗਏ ਕਾਰਾਂ ਨੂੰ ਦਿਖਾ ਸਕਦਾ ਹੈ। ਇਸ ਨਾਲ ਤੁਹਾਨੂੰ ਸਪਸ਼ਟ ਤਸਵੀਰ ਮਿਲਦੀ ਹੈ ਕਿ ਏਜੰਟ ਕਿਵੇਂ ਇੰਟਰੈਕਟ ਕਰ ਰਹੇ ਹਨ ਅਤੇ ਕੀ ਯੂਜ਼ਰ ਦੀਆਂ ਪਸੰਦਾਂ ਅਤੇ ਸੀਮਾਵਾਂ ਪੂਰੀਆਂ ਹੋ ਰਹੀਆਂ ਹਨ।

ਆਓ ਹਰ ਇਕ ਪੱਖ ਨੂੰ ਵਧੇਰੇ ਵਿਸਥਾਰ ਨਾਲ ਵੇਖੀਏ।

- **ਲੌਗਿੰਗ ਅਤੇ ਮਾਨੀਟਰਿੰਗ ਟੂਲ**: ਤੁਸੀਂ ਹਰ ਏਜੰਟ ਵੱਲੋਂ ਕੀਤੇ ਗਏ ਹਰ ਕੰਮ ਦੀ ਲੌਗਿੰਗ ਕਰਵਾਉਣੀ ਚਾਹੁੰਦੇ ਹੋ। ਲੌਗ ਵਿੱਚ ਇਹ ਜਾਣਕਾਰੀ ਹੋ ਸਕਦੀ ਹੈ ਕਿ ਕਿਹੜੇ ਏਜੰਟ ਨੇ ਕੰਮ ਕੀਤਾ, ਕੀ ਕੰਮ ਕੀਤਾ, ਕਦੋਂ ਕੀਤਾ ਅਤੇ ਨਤੀਜਾ ਕੀ ਸੀ। ਇਹ ਜਾਣਕਾਰੀ ਡਿਬੱਗਿੰਗ, ਅਪਟੀਮਾਈਜ਼ੇਸ਼ਨ ਅਤੇ ਹੋਰ ਲਈ ਵਰਤੀ ਜਾ ਸਕਦੀ ਹੈ।
- **ਵਿਜ਼ੂਅਲਾਈਜ਼ੇਸ਼ਨ ਟੂਲ**: ਇਹ ਟੂਲ ਤੁਹਾਨੂੰ ਏਜੰਟਾਂ ਵਿਚਕਾਰ ਇੰਟਰੈਕਸ਼ਨ ਨੂੰ ਵਧੇਰੇ ਸਮਝਣਯੋਗ ਢੰਗ ਨਾਲ ਵੇਖਣ ਵਿੱਚ ਮਦਦ ਕਰਦੇ ਹਨ। ਉਦਾਹਰਨ ਵਜੋਂ, ਤੁਸੀਂ ਇੱਕ ਗ੍ਰਾਫ ਦੇਖ ਸਕਦੇ ਹੋ ਜੋ ਏਜੰਟਾਂ ਵਿਚਕਾਰ ਜਾਣਕਾਰੀ ਦੇ ਪ੍ਰਵਾਹ ਨੂੰ ਦਿਖਾਉਂਦਾ ਹੈ। ਇਹ ਤੁਹਾਨੂੰ ਬੋਤਲਨੈਕ, ਅਕਾਰਗਤਾ ਅਤੇ ਹੋਰ ਸਮੱਸਿਆਵਾਂ ਪਛਾਣਨ ਵਿੱਚ ਮਦਦ ਕਰ ਸਕਦਾ ਹੈ।
- **ਪ੍ਰਦਰਸ਼ਨ ਮੈਟਰਿਕਸ**: ਇਹ ਮੈਟਰਿਕਸ ਤੁਹਾਨੂੰ ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮ ਦੀ ਪ੍ਰਭਾਵਸ਼ੀਲਤਾ ਟਰੈਕ ਕਰਨ ਵਿੱਚ ਮਦਦ ਕਰਦੇ ਹਨ। ਉਦਾਹਰਨ ਵਜੋਂ, ਤੁਸੀਂ ਕੰਮ ਮੁਕੰਮਲ ਕਰਨ ਵਿੱਚ ਲੱਗਣ ਵਾਲਾ ਸਮਾਂ, ਪ੍ਰਤੀ ਇਕਾਈ ਸਮਾਂ ਵਿੱਚ ਮੁਕੰਮਲ ਹੋਏ ਕੰਮਾਂ ਦੀ ਗਿਣਤੀ, ਅਤੇ ਏਜੰਟਾਂ ਵੱਲੋਂ ਦਿੱਤੀਆਂ ਸਿਫਾਰਸ਼ਾਂ ਦੀ ਸਹੀਤਾ ਟਰੈਕ ਕਰ ਸਕਦੇ ਹੋ। ਇਹ ਜਾਣਕਾਰੀ ਤੁਹਾਨੂੰ ਸੁਧਾਰ ਲਈ ਖੇਤਰ ਪਛਾਣਨ ਅਤੇ ਸਿਸਟਮ ਨੂੰ ਅਪਟੀਮਾਈਜ਼ ਕਰਨ ਵਿੱਚ ਮਦਦ ਕਰਦੀ ਹੈ।

## ਮਲਟੀ-ਏਜੰਟ ਪੈਟਰਨ

ਆਓ ਕੁਝ ਠੋਸ ਪੈਟਰਨਾਂ ਵਿੱਚ ਡੁੱਬਕੀ ਲਗਾਈਏ ਜੋ ਅਸੀਂ ਮਲਟੀ-ਏਜੰਟ ਐਪ ਬਣਾਉਣ ਲਈ ਵਰਤ ਸਕਦੇ ਹਾਂ। ਇੱਥੇ ਕੁਝ ਦਿਲਚਸਪ ਪੈਟਰਨ ਹਨ ਜੋ ਵਿਚਾਰ ਕਰਨ ਯੋਗ ਹਨ:

### ਗਰੁੱਪ ਚੈਟ

ਇਹ ਪੈਟਰਨ ਉਸ ਵੇਲੇ ਲਾਭਦਾਇਕ ਹੁੰਦਾ ਹੈ ਜਦੋਂ ਤੁਸੀਂ ਇੱਕ ਗਰੁੱਪ ਚੈਟ ਐਪ ਬਣਾਉਣਾ ਚਾਹੁੰਦੇ ਹੋ ਜਿੱਥੇ ਕਈ ਏਜੰਟ ਇਕ ਦੂਜੇ ਨਾਲ ਗੱਲਬਾਤ ਕਰ ਸਕਦੇ ਹਨ। ਇਸ ਪੈਟਰਨ ਦੇ ਆਮ ਵਰਤੋਂ ਦੇ ਮਾਮਲੇ ਟੀਮ ਸਹਿਯੋਗ, ਗਾਹਕ ਸਹਾਇਤਾ ਅਤੇ ਸੋਸ਼ਲ
## ਪਿਛਲਾ ਪਾਠ

[ਯੋਜਨਾ ਡਿਜ਼ਾਈਨ](../07-planning-design/README.md)

## ਅਗਲਾ ਪਾਠ

[ਏਆਈ ਏਜੰਟਾਂ ਵਿੱਚ ਮੈਟਾਕੌਗਨੀਸ਼ਨ](../09-metacognition/README.md)

**ਅਸਵੀਕਾਰੋਪਣ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦਿਤ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀਤਾ ਲਈ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਰੱਖੋ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸਮਰਥਤਾਵਾਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਆਪਣੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਪ੍ਰਮਾਣਿਕ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਉਤਪੰਨ ਕਿਸੇ ਵੀ ਗਲਤਫਹਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।