<template>
  <header class="header">
    <div class="container header__container">
      <button class="burger btn-reset header__burger">
        <span class="burger__line"></span>
      </button>
      <nav class="nav header__nav">
        <ul class="nav__list">
          <li class="nav__item">
            <RouterLink class="main-link nav__link" to="/">Home</RouterLink>
          </li>
          <li class="nav__item">
            <RouterLink class="main-link nav__link" to="/">Shop</RouterLink>
          </li>
          <li class="nav__item">
            <RouterLink class="main-link nav__link" to="/">Elements</RouterLink>
          </li>
          <li class="nav__item">
            <RouterLink class="main-link nav__link" to="/">Blog</RouterLink>
          </li>
          <li class="nav__item">
            <RouterLink class="main-link nav__link" to="/">Page</RouterLink>
          </li>
        </ul>
        <button class="nav__close btn-reset">закрыть</button>
      </nav>
      <a href="#" class="logo header__logo" aria-label="logo">
        <img src="../../public/logo.svg" alt="" />
      </a>
      <ul class="shop-nav header__shop-nav">
        <li class="shop-nav__item">
          <form action="#" class="shop-nav__search-form search-form">
            <button class="search-form__btn btn-reset" aria-label="Find"></button>
          </form>
        </li>
        <li class="shop-nav__item">
          <a href="#" class="shop-nav__link shop-nav__link--user" aria-label="Go to cabinet"></a>
        </li>
        <li class="shop-nav__item">
          <a href="#" class="shop-nav__link cart" aria-label="Go to cart">
            <span class="cart__icon"></span>
            <span class="cart__quantity quantity">3</span>
          </a>
        </li>
      </ul>
    </div>
  </header>
</template>

<style scoped lang="scss">
@import '../assets/scss/main.scss';
.nav {
  &__list {
    display: flex;

    @include md {
      display: block;
    }
  }

  &__item {
    &:not(:last-child) {
      margin-right: 45px;

      @include md {
        margin-right: 0;
      }
    }
    cursor: pointer;
  }

  &__link {
    &:hover {
      @include md {
        &::before {
          opacity: 0;
        }
      }
    }

    &--current {
      &::before {
        opacity: 1;
        transition: opacity 0.15s;

        @include md {
          opacity: 0;
        }
      }
    }

    @include md {
      display: inline-block;
      border-bottom: 1px solid #bfbfbf;
      padding: 10px 10%;
      width: 100%;
      font-size: 19px;
    }
  }

  &--visible {
    left: 0;
    transition: left 0.3s;
  }
}
.shop-nav {
  display: flex;
  align-items: center;

  &__item {
    &:not(:last-child) {
      margin-right: 25px;

      @include xs {
        margin-right: 15px;
      }
    }
  }

  &__link {
    display: inline-block;
    width: 16px;
    height: 16px;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    transition: opacity 0.3s;

    &:hover {
      opacity: 0.7;
      transition: opacity 0.3s;
    }

    &--user {
      background-image: url('../../../../public/user.png');
    }
  }
}

.cart {
  width: auto;
  height: auto;

  &__icon {
    display: inline-block;
    width: 16px;
    height: 16px;
    background-image: url('../../../../public/cart.png');
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
  }
}

.search-form {
  &__btn {
    display: inline-block;
    width: 16px;
    height: 16px;
    background-image: url('../../../../public/search.png');
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    transition: opacity 0.3s;

    &:hover {
      opacity: 0.7;
      transition: opacity 0.3s;
    }
  }
}

.quantity {
  display: inline-flex;
  align-items: center;
  border-radius: 25px;
  padding: 0 5px;
  height: 16px;
  font-weight: 700;
  font-size: 10px;
  color: var(--color-white);
  background-color: var(--color-dark);
}
.header {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 100;
  width: 100%;

  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: 36px;
    padding-bottom: 36px;

    @include xs {
      padding: 20px 15px;
    }
  }

  &__shop-nav {
    margin-left: 250px;

    @include md {
      margin-left: 0;
    }
  }
}

.logo {
  display: inline-block;
  width: 117px;
  height: 22px;

  svg {
    display: block;
    width: 100%;
    height: 100%;
    fill: var(--color-dark);
    object-fit: cover;
  }

  @include xs {
    width: 90px;
    height: 18px;
  }
}

.catalog-header {
  padding-top: 38px;

  @include xs {
    padding-top: 0;
  }
}

.free-delivery {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 120;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 40px;
  font-size: 10px;
  text-transform: uppercase;
  color: var(--color-white);
  background-color: #111;

  &__btn {
    position: absolute;
    right: 40px;
    top: 50%;
    width: 12px;
    height: 12px;
    transform: translateY(-50%);

    svg {
      display: block;
      width: 100%;
      height: 100%;
      fill: var(--color-white);
    }
  }

  @include xs {
    display: none;
  }
}

.card-page {
  .header {
    padding-top: 0;
  }
}

.nav {
  &__close {
    display: none;

    @include md {
      position: absolute;
      right: 10%;
      top: 4%;
      display: block;
    }
  }

  @include md {
    position: fixed;
    left: -150vw;
    top: 0;
    padding: 10% 0;
    width: 80%;
    height: 100vh;
    background-color: #fff;
    transition: left 0.3s;
  }
}

.burger {
  position: relative;
  display: none;
  width: 25px;
  height: 18px;

  &::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 2px;
    background-color: var(--color-dark);
  }

  &::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    background-color: var(--color-dark);
  }

  &__line {
    position: absolute;
    left: 0;
    top: 50%;
    width: 100%;
    height: 2px;
    background-color: var(--color-dark);
    transform: translateY(-50%);
  }

  @include md {
    display: block;
  }
}
</style>
