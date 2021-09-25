<script>

import translations from '../data/translations';
import {
    dict,
    locale,
    t
} from '../data/i18n';
$: languages = Object.keys(translations);
$: dict.set(translations);

export let message;
var count = 200;
var defaults = {
    origin: {
        y: 0.7
    }
};

function fire(particleRatio, opts) {
    confetti(Object.assign({}, defaults, opts, {
        particleCount: Math.floor(count * particleRatio)
    }));
}
fire(0.25, {
    spread: 26,
    startVelocity: 55,
});
fire(0.2, {
    spread: 60,
});
fire(0.35, {
    spread: 100,
    decay: 0.91,
    scalar: 0.8
});
fire(0.1, {
    spread: 120,
    startVelocity: 25,
    decay: 0.92,
    scalar: 1.2
});
fire(0.1, {
    spread: 120,
    startVelocity: 45,
});
fire(0.25, {
    spread: 26,
    startVelocity: 55,
});
fire(0.2, {
    spread: 60,
});
fire(0.35, {
    spread: 100,
    decay: 0.91,
    scalar: 0.8
});
fire(0.1, {
    spread: 120,
    startVelocity: 25,
    decay: 0.92,
    scalar: 1.2
});
fire(0.1, {
    spread: 120,
    startVelocity: 45,
});
</script>

<div class="surprise w-auto h-autoflex flex-col items-center justify-center">
    <h1 class="text-2xl lg:text-4xl text-center font-semibold">
        {message} 🎉
    </h1>
    <p class="text-center font-normal">
        {$t('form_submit')[0].desc}
    </p>
</div>

  <style>
  </style>
